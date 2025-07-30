```SQL
SELECT title 
FROM movies 
WHERE id IN (
    SELECT movie_id 
    FROM stars 
    WHERE person_id = (SELECT id FROM people WHERE name = 'Jennifer Lawrence')
)
INTERSECT
SELECT title 
FROM movies 
WHERE id IN (
    SELECT movie_id 
    FROM stars 
    WHERE person_id = (SELECT id FROM people WHERE name = 'Bradley Cooper')
);
```

The above query will give the movies that star both *Jennifer Lawrence* and *Bradley Cooper*.
A better version would utilize `JOIN` and `GROUP BY`s:
```SQL
SELECT m.title
FROM movies m
JOIN stars s1 ON m.id = s1.movie_id
JOIN people p1 ON s1.person_id = p1.id
JOIN stars s2 ON m.id = s2.movie_id
JOIN people p2 ON s2.person_id = p2.id
WHERE p1.name = 'Jennifer Lawrence'
  AND p2.name = 'Bradley Cooper';
```

Even more cleaner version, if we're checking multiple actors:
```SQL
SELECT m.title
FROM movies m
JOIN stars s ON m.id = s.movie_id
JOIN people p ON s.person_id = p.id
WHERE p.name IN ('Jennifer Lawrence', 'Bradley Cooper')
GROUP BY m.id, m.title
HAVING COUNT(DISTINCT p.name) = 2;
```
Let’s **break this query down step-by-step** so you understand exactly what it's doing. The goal of this query is to **find all movies where both Jennifer Lawrence and Bradley Cooper acted** together.

---

## 🔍 Step-by-Step Explanation

---

### 1. **FROM and JOINs**

```sql
FROM movies m
JOIN stars s ON m.id = s.movie_id
JOIN people p ON s.person_id = p.id
```

- We’re starting from the `movies` table and giving it an alias `m`.
    
- We're joining the `stars` table, which tells us **who acted in which movie**.
    
    - `s.movie_id = m.id` links each movie to its stars.
        
- We then join the `people` table, which contains **actor names**.
    
    - `s.person_id = p.id` gives us the name of each actor in a movie.
        

At this point, we have a table where each row tells us:  
**(movie title, actor name)**

---

### 2. **WHERE clause**

```sql
WHERE p.name IN ('Jennifer Lawrence', 'Bradley Cooper')
```

- This filters the rows so that we only keep rows where the actor is **either** Jennifer Lawrence **or** Bradley Cooper.
    
- So now we have a list of movies where **either one** of them acted.
    

> Note: This doesn’t yet guarantee both of them are in the same movie.

---

### 3. **GROUP BY clause**

```sql
GROUP BY m.id, m.title
```

- We're grouping all rows **by each movie**.
    
- So now, for each movie, we’ll process all the actors (from the previous filtered list) who acted in it.
    

---

### 4. **HAVING clause**

```sql
HAVING COUNT(DISTINCT p.name) = 2
```

- `COUNT(DISTINCT p.name)` counts how many **distinct** names (from our list of 2) are present in each movie.
    
- We're only selecting the movies that have **both names** (Jennifer **and** Bradley), not just one.
    

---

## ✅ Final Result

You get a list of `m.title` — movie titles — where:

- Both Jennifer Lawrence and Bradley Cooper acted together.
    
- Even if the movie had 100 other actors, it only passes if **these two** are in it.
    

---

### 🧠 Real Example:

|Movie|Actor|
|---|---|
|Silver Linings Playbook|Jennifer Lawrence|
|Silver Linings Playbook|Bradley Cooper|
|American Hustle|Bradley Cooper|
|American Hustle|Jennifer Lawrence|
|X-Men: First Class|Jennifer Lawrence|

→ After filtering and grouping:

- **Silver Linings Playbook** → Has both → ✅
    
- **American Hustle** → Has both → ✅
    
- **X-Men** → Only Jennifer → ❌
    