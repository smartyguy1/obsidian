To assist in working with SQL in this course, the CS50 library can be utilized as:
```python
from cs50 import SQL
```

We can write `favorites.py` as follows:
```python
# searches for database popularity of a problem

from cs50 import SQL

#Open database
db = SQL("sqlite:///favorites.db")

#Prompt user for favorite
favorite = input("Favorite: ")

rows = db.execute("SELECT COUNT(*) AS n FROM favorites WHERE language = ?", favorite)

# Get first (and only) row
row = rows[0]

print(row["n"])
```

