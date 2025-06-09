
# Reading from a File

An incredible amount of data is available in text files. When we want to work with information in a text file, the first step is to read the file into memory. We can read the entire contents of a file or we can work through the file one line at a time.

## Reading an Entire File
Let there be a text file called `pi_digits.txt` that contains $\pi$ to 30 decimal places, with 10 decimal places per line:
```
3.1415926535
  8979323846
  2643383279
```

To open the file:
```python
with open('pi_digits.txt') as file_object:
	contents = file_object.read()
print(contents)
```
Make sure that the file is in the same directory as the python program.

The `open()` function needs one argument: the name of the file you want to open. Python looks for this file in the directory of the program. The `open()` returns an object representing the file. Here, `open('pi_digits.txt')` returns an object representing  `pi_digits.txt`. Python assigns this object to `file_object`, which we'll work with later in the program.

The keyword `with` closes the file once access to it is no longer needed. We could open and close the file by calling `open()` and `close()` but if a bug in our program prevents the file from being closed, it can cause data-loss or corruption. And if we call `close()` too early we will not be able to access the file again in the program.

The `read()` method reads the entire contents of the file and store it as one long string in `contents`.

The only difference between this output and the original file is the extra blank like at the end of the output. The blank line appears because `read()` returns an empty string when it reaches the end of the file.
We can remove the extra blank line with `.rstrip()`.
## File Paths
If our file is not in the directory of our program but in a folder that is in that directory:
```python
with open('text_files/filename.txt') as file_object:
```
This line tells python to look for the desired *.txt* file in the folder *text_filer* and assumes that *text_folder* is located inside the directory of the program.

If it is located somewhere else:
```python
file_path = '/home/ehmatthes/other_files/text_files/filename.txt'
with open(file_path) as file_object:
```

## Reading by line
```python
filename = 'pi_digits.txt'
with open(filename) as file_object:
	for line in file_object:
		print(line.rstrip())
```
OR
```python
with open(filename) as file_object:
	lines = file_object.readlines()

for line in lines:
	print(line.rstrip())
```
The `readlines()` methods takes each line from the file and stores it in a list.

# Writing to a File
We use `write()` method to write to  file.
```python
filename = 'programming.txt'

with open(filename, 'w') as file_object:
	file_object.write("I love programming.")
```
This call to `open()` in this example has two arguments. The First is the filename and the second `'w'` tells Python that we want to open the file in *write mode*. We can open a file in *read mode*(`'r'`), *write mode*(`'w'`), *append mode* (`'a'`) or a mode that allows you to read and write to the file (`'r+'`).
If we omit the mode argument, python opens the file in read-only mode by default.

The `open()` function automatically creates the file we're writing to if it doesn't exist. However, be careful opening a file in write mode(`'w'`) because if it does exist, python will erase the contents of the file before returning the file object.

## Writing Multiple Lines
The `write()` function doesn't add any new lines to the text that we write. So we need to write with new-line characters.
```python
filename = 'programming.txt'
with open(filename, 'w') as file_object:
	file_object.write("I love programming.\n")
	file_object.write("I love creating new games.\n")
```

## Appending a File

In append mode (`'a'`) python does not write over existing content, i.e. it doesn't erase the contents of the file before returning the file object.
Any lines we add to the file will be added to the end of the line. If the file doesn't exist, python will open the file for us.

```python
filename = 'programming.txt'

with open(filename, 'a') as file_object:
	file_object.write("I also love finding meaning in large datasets.\n")
	file_object.write("I love creating apps that can run in a browser.\n")
```

# Exceptions

Python uses special objects called *exceptions* to manage errors that arise during a program's execution. Whenever an error occurs that makes python unsure what to do next, it creates an exception object. If you write code that handles the exception, the program will halt and show a *traceback*, which includes a report of the exception that was raised.

Exceptions are handled with `try-except` blocks. A `try-except` block asks python to do something, but it also tells python what to do if an exception is raised.
When we use `try-except` blocks our programs will continue running even if there is an error and instead of tracebacks which are confusing for users to read, users will see friendly error messages that we write.

## Handling the ZeroDivisionError Exception
```python
print(5/0)
```
output:
```
Traceback (most recent call last):
File "division_calculator.py", line 1, in <module>
	print(5/0)
ZeroDivisionError: division by zero
```

## Using try-except Blocks
```python
try:
	print(5/0)
except ZeroDivisionError:
	print("You can't divide by zero!")
```
If a code inside a `try` block works, python skips over the `except` block. If the code in the `try` block causes an error, Python looks for an except block whose error matches the one that was raised and runs the code in that block.