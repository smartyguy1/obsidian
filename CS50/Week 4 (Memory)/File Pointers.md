- The ability to read data from and write data into files is the primary means of storing **persistent data**, data that does not disappear when your program stops running.
- The abstraction of files that C provides is implemented in a data structure known as a `FILE`.
	- Almost universally when working with files, we will be using pointers to the, `FILE*`.

- The file manipulation functions all are in `stdio.h`
	- All of them accept `FILE*` as one of their parameters, except for the function `fopen()`, which is used to get a file pointer in the first place.

Some common [[Input#^1acb0d|file I/O]] functions:
- `fopen()`
- `fclose()`
- `fgetc()`
- `fread()`
- `fwrite()`

# `fopen()`
- Opens a file and returns a file pointer to it.
- Always check the return value to make sure you don't get back `NULL`.
```
FILE* ptr = fopen(<filename>, <operation>);
```
Eg:
```C
FILE* ptr1 = fopen("file1.txt", "r");
FILE* ptr2 = fopen("file2.txt", "w");
FILE* ptr3 = fopen("file3.txt", "a");
```
# `fclose()`
- Closes the file pointed to by the given pointer.
```
fclose(<file pointer>);
```
Eg:
```C
fclose(ptr1);
```

# `fgetc()`
- Read and return the next character from the file pointed to.
- Note: The operation of the file pointer passed in as a parameter must be `"r"` for read, or we will get an error.
```
char ch = fgetc(<file pointer>);
```
Eg:
```C
char ch = fgetc(ptr1);
```

If we put this in a loop we could read all the character from a file and print them to the screen, one-by-one,:
```C
char c;
while ((ch = fgetc(ptr)) != EOF) //EOF stands for End Of File object
	printf("%c", ch);
```
This simply *catenates* the contents in the terminal,same as what the linux command `cat` does just this.
# `fputc()`
- Writes or appends the specified character to the pointed-to file.
- Note: The operation of the file pointer passed in as a parameter must be `"w"` for write or `"a"` for append, or we will suffer an error.
```
fputc(<character>, <file pointer>);
```

Eg:
```C
fputc('A', ptr2);
fputc('!', ptr3);
```

We can copy the contents of a file:
```C
char ch;
while ((ch = fgetc(ptr)) != EOF)
	fputc(ch, ptr2);
```
This does what the linux command `cp` does.

# `fread()`
- Reads `<qty>` units of size `<size>` from the file pointed to and stores them in memory in a buffer(usually an array) pointed to by `<buffer>`.
- Note: The operation of the file pointer passed is as a parameter must be `"r"` for read, or you will suffer an error.
```
fread(<buffer>, <size>, <qty>, <file pointer>);
```
Eg:
```C
int arr[10];
fread(arr, sizeof(int), 10, ptr);
```
Eg:
```C
double* arr2 = malloc(sizeof(double)*80);
fread(arr2, sizeof(double), 80, ptr);
```
Eg:
```C
char c;
fread(&c, sizeof(char), 1, ptr);
```
# `fwrite()`
- Writes `<qty>` units of size `<size>` to the file pointed to by reading them from a buffer (usually an array) pointed to by `<buffer>`.
- Note: The operation of the file pointer passed in as a parameter must be `"w"` for write or `"a"` for append, or you will suffer an error.
```
fwrite(<buffer>, <size>, <qty>, <file pointer>);
```
Eg:
```C
int arr[10];
fwrite(arr, sizeof(int), 10, ptr);
```
Eg:
```C
double* arr2 = malloc(sizeof(double)*80);
fwrite(arr2, sizeof(double), 80, ptr);
```
Eg:
```C
char c;
fwrite(&c, sizeof(char), 1, ptr);
```

Some more useful functions:

| Function    | Description                                                    |
| ----------- | -------------------------------------------------------------- |
| `fgets()`   | Reads a full string from a file                                |
| `fputs`     | Writes a full string to a file                                 |
| `fprintf()` | Writes a formatted string to a file.                           |
| `fseek()`   | Allows you rewind or fast-forward within a file                |
| `ftell()`   | Tells you at what (byte) position you are at within a file.    |
| `feof()`    | Tells you whether you’ve read to the end of a file             |
| `ferror()`  | Indicates whether an error has occurred in working with a file |




