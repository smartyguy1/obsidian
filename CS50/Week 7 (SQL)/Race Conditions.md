Utilizing SQL database can result in some problems:
When multiple users are accessing the same database and executing commands at the same time--This could result in glitches where code is interrupted by other people's actions. This could result in a loss of data.

Built-in SQL features such as `BEGIN TRANSACTION`, `COMMIT` and `ROLLBACK` help avoid some of these race condition problems.
```PYTHON
db.execute("BEGIN TRANSACTION")
rows = db.execute("SELECT likes FROM posts WHERE id = ?;", id)
likes = rows[0]["likes"]
db.execute("UPDATE posts SET likes = ? WHERE id = ?;", likes+1, id)
db.execute("COMMIT")
```
