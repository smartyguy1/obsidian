# `SELECT`
```SQL
SELECT COUNT(*) FROM favorites WHERE language = 'C';
```
Returns the number of rows where `language` column contains `c`.

```SQL
SELECT language, COUNT(*) FROM favorites WHERE language = 'C' AND problem = 'Hello, World';
```
The `AND` is utilized to narrow our result.

```SQL
SELECT language, COUNT(*) FROM favorites GROUP BY language;
```
This will return a temporary table that shows the language and the count

```SQL
SELECT language, COUNT(*) FROM favorites GROUP BY language ORDER BY COUNT(*);
```
This sorts(or orders) the above table.

```SQL
SELECT COUNT(*) FROM favorites WHERE language = 'C' AND (problem = 'Hello, World' OR problem = 'Hello, It''s Me');
```
To put a single `'` inside a string in SQL, we need to put two `''`.

```SQL
SELECT COUNT(*) FROM favorites WHERE language = 'C' AND problem LIKE 'Hello, %';
```
This query will find any problems that start with `Hello, ` (including a space).

```SQL
SELECT language, COUNT(*) AS n FROM favorites GROUP BY language ORDER BY n DESC;
```
OUTPUT:
```
+----------+-----+
| language |  n  |
+----------+-----+
| Python   | 280 |
| C        | 78  |
| Scratch  | 40  |
+----------+-----+
```

```SQL
SELECT language, COUNT(*) AS n FROM favorites GROUP BY language ORDER BY n DESC LIMIT 1;
```

OUTPUT:
```
+----------+-----+
| language |  n  |
+----------+-----+
| Python   | 280 |
+----------+-----+
```

# `INSERT`

We can insert data into a table using: `INSERT INTO table (column...) VALUES(value,...);`
For example:
```SQL
INSERT INTO favorites (language, problem) VALUES ('SQL', 'Fiftyville');
SELECT * FROM favorites;
```
Output:
```
| 10/30/2023 13:40:48 | Python   | Scratch        |
| 10/30/2023 13:40:58 | Python   | Cash           |
| 10/30/2023 13:40:59 | C        | Sort           |
| 10/30/2023 13:41:03 | C        | Mario          |
| 10/30/2023 13:41:05 | C        | Inheritance    |
| 10/30/2023 13:41:09 | C        | Sort           |
| 10/30/2023 13:41:21 | C        | Sort           |
| NULL                | SQL      | Fiftyville     |
+---------------------+----------+----------------+
```

# `DELETE`

Allows us to delete parts of our data. For example:
```SQL
DELETE FROM favorites WHERE Timestamp is NULL;
```
This deletes any record where the Timestamp is `NULL`.

# `UPDATE`
We can also utilize the `UPDATE` command to update our data.
For example:
```SQL
UPDATE favorites SET language = 'SQL', problem = 'Fiftyville';
```
This will result in overwriting all previous statements where C and scratch were the programming languages.

# Example database
IMDb offers a database of people, shows, writers, stars, genres and ratings. Each of these tables is related to one another as follows:
![[Pasted image 20250707113206.png]]
To get a list of shows that have a rating $\geq$ 6.0, we can run the query:
```SQL
SELECT title FROM shows WHERE id IN(
SELECT show_id FROM ratings WHERE rating >= 6.0 LIMIT 10
);
```
This query nests together two queries. An inner query is used by an outer query

# `JOIN`

We can combine two tables temporarily using the `JOIN` keyword. For example, we can rewrite the above query as:
```SQL
SELECT title from shows
JOIN shows ON shows.id = ratings.shows_id
WHERE rating >= 6.0
LIMIT 10;
```

```SQL
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate  
FROM Orders  
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```
## Different Types of SQL JOINs

Here are the different types of the JOINs in SQL:

- `(INNER) JOIN`: Returns records that have matching values in both tables
- `LEFT (OUTER) JOIN`: Returns all records from the left table, and the matched records from the right table
- `RIGHT (OUTER) JOIN`: Returns all records from the right table, and the matched records from the left table
- `FULL (OUTER) JOIN`: Returns all records when there is a match in either left or right table

![SQL INNER JOIN](https://www.w3schools.com/sql/img_inner_join.png)  ![SQL LEFT JOIN](https://www.w3schools.com/sql/img_left_join.png)  ![SQL RIGHT JOIN](https://www.w3schools.com/sql/img_right_join.png)  ![SQL FULL OUTER JOIN](https://www.w3schools.com/sql/img_full_outer_join.png)
# 

We can search for the *The Office* and the  actors in that show by executing the following command:
```SQL
SELECT name FROM people WHERE id IN 
	(SELECT person_id FROM stars WHERE show_id = 
		(SELECT id FROM shows WHERE title = 'The Office' AND year = 2005));
```

We can find all the shows Steve Carell starred in by:
```SQL
SELECT title FROM shows WHERE id IN
	(SELECT show_id FROM stars WHERE person_id =
		(SELECT id FROM people WHERE name = 'Steve Carell'));
```

This could also be expressed in this way:
```SQL
SELECT title FROM shows, stars, people
WHERE shows.id = stars.show_id
AND stars.person_id = people.id
AND people.name = 'Steve Carell';
```

# `INTERSECT` Clause
The INTERSECT clause in SQL is used to combine two `SELECT` statements but the dataset returned by the **INTERSECT statement*** will be the intersection of the data sets of the two SELECT statements In simple words, the INTERSECT statement will return only those rows that will be common to both of the SELECT statements.

**Syntax**:
```SQL
SELECT column1 , column2 ....  
FROM table1  
WHERE condition  
INTERSECT  
SELECT column1 , column2 ....  
FROM table2  
WHERE condition
```
