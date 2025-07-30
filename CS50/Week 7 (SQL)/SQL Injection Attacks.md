An injection attack is where a malicious actor could input malicious SQL code.
For example, consider a login screen:
![[Pasted image 20250707122535.png]]
Without proper protection in our own code, a bad actor could run malicious code.
Consider the following code:
```python
rows = db.execute("SELECT COUNT(*) FROM users WHERE username = ? AND password = ?", username, password)
```
Notice that because `?` is in place, validation can be run on `favorite` before it is blindly accepted by the query.
Never utilize formatted strings as above or blindly trust the user's input.
Utilizing the CS50 Library, the library will sanitize and remove the potentially malicious characters.