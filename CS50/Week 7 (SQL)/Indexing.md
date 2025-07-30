
While relational databases have the ability to be more faster than `csv` file, data cam be optimized within a table using *indexes*.
Indexes can be utilized to speed up our queries.
We can track the speed of our queries by executing `.timer on` in `sqlite3`.

We can create an index using the syntax:
`CREATE INDEX title_index ON shows(title);` This tells `sqlite3` to create an index and perform some special under-the-hood optimization relating to this column `title`.

This creates a data structure called a **B Tree**, a data structure that looks like a binary tree. However, unlike binary tree, there can be more than two child nodes.
![[Pasted image 20250707115946.png]]

Further, we can create indexes as follows:
```SQL
CREATE INDEX name_index ON people (name);
CREATE INDEX person_index ON stars (person_id);
```

Running this query and you will notice that is runs much more quickly:
```SQL
SELECT title FROM shows WHERE id IN
	(SELECT show_id FROM stars WHERE person_id =
		(SELECT id FROM people WHERE name = 'Steve Carell'));
```
