# Flat-File Database

Data can be described in patterns of columns and rows. Spreadsheets can be outputted to a `csv` file.
In `csv` files, all data is stored row by row. Each column is separated by a comma or another value. However, accessing and querying `csv` files using python can get pretty arduous, with for loops and conditionals.

# Relational Databases
Google, X, and Meta all use relational databases to store their information at scale. Relational databases store data in rows and columns in structures called tables.
SQL allows for four types of commands:
```
Create
Read
Update
Delete
```
These four operations are called *CRUD*'
- We can create a table with SQL syntax `CREATE TABLE table (column type, ...);`. In `sqlite3`, we can create a database at the terminal by typing `sqlite3 favorites.db`.
- We can put `sqlite` into `csv` mode by typing `.mode csv`. Then, we can import our data from our `csv` file by typing `.import favorites.csv favorites`
- We can type `.schema` to see the structure of the database.
- We can read Items from a tables using the syntax: `SELECT columns FROM table;`. For example: using the command `SELECT * FROM favorites;` will print every row in `favorites`.

SQL supports many commands to access data, including:
```SQL
AVG
COUNT 
DISTINCT
LOWER
MAX
MIN
UPPER
```
- For example, you can type `SELECT COUNT(*) FROM favorites;`. Further, you can type `SELECT DISTINCT language FROM favorites;` to get a list of the individual languages within the database. You can even type `Select COUNT(DISTINCT language) FROM favorites;` to get a count of those.
- SQL also offers additional commands we can utilize in our queries:
```SQL
WHERE -- adding a Boolean expression to filter our data
LIKE -- filtering responses more loosely
ORDER BY -- ordering responses
LIMIT -- limiting the number of responses
GROUP BY -- grouping responses together
```
