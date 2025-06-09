
# Strings

A string is a series of characters. Anything inside quotes is considered a string in python.
### Changing case in string with methods
```python
name = "ada lovelace"
print(name.title())
```
```
Ada Lovelace
```

```python
print(name.upper())
print(name.lower())
```

```
ADA LOVELACE
ada lovelace
```

### Using variables in strings
```python
f_name = "ada"
l_name = "lovelace"
full_name = f"{f_name}{l_name}"
print(full_name)
```
These strings are called *f-strings*. The *f* is for *format*, because Python formats the string by replacing the name of any variable in braces with its value.
output:
```
ada lovelace
```
we can fo a lot with f strings
eg:
```python
print(f"Hello, {full_name.title()}!")
```
```
Hello, Ada Lovelace!
```

### Adding whitespace to strings with tabs or Newline
>Follow ASCII
>	\\n for new line
>	\\t for adding tab
>	\\n\\t move to a new line and start the line with tab

### Stripping Whitespace

To remove whitespace from the right-side of the string we use `r_strip()` method.
```python
fav_lang = 'python '
print(fav_lang.rstrip())
print(fav_lang)
```
```
'python'
'python '
```
 similarly,
 ```python
 fav_lang = ' python '
 print(fav_lang.rstrip())
 print(fav_lang.lstrip())
 print(fav_lang.strip())
```
```
' python'
'python '
'python'
```

# Numbers
- Integers
- Floats
Both are easily inter-convertible. 
When writing large numbers, we can group digits using underscores `_` to make them more readable.
```python
>>>universe_age = 14_000_000_000
>>>print(universe_age)
```
```
14000000000
```
operators:
```python
x*y #multiplication
x**y #exponentiation x^y
x+y
x-y
```

Multiple Assignments :
```python
x,y,z = 0,0,0
```

Constants:
Write variable name in  all capitals and python will recognize it as a constant variable.
```python
MAX_CONNECTIONS = 5000
```
