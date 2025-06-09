# Command line argument in python
```python
from sys import argv

if len(argv) == 2:
	print(f"hello, {argv[1]}")
else:
	print("Hello, world")
```
# Exit status
```python
import sys

if len(sys.argv) != 2:
	print("Missing command-line argument")
	sys.exit(1)
print(f"hello, {sys.argv[1]}")
sys.exit(0)
```