# Linear Search

^81a9de

Suppose we have an array of size n and we want to find if the number 50 is in it.
If it is, then return true and if it is not then return false.

We could write a pseudocode in the following manner to implement this algorithm
```
for i from 0 to n-1:
	if 50 in array[i]:
		return true;
return false
```
The process is very simple. ==The computer will check each element one after the another to see if it is equal to 50 , if anyone is it would return **true**, and if none are it would return **false**.==

# Binary Search

^45a3ac

Another useful algorithm for searching is **Binary Search**.

Assuming that the values in the array have been arranged from smallest to largest, We can write the pseudocode as follows:
```
if value left
	return false;
if 50 == array[middle]:
	return true;
else if 50 < array[middle]:
	search array from 0 to m-1;
else if 50 > array[middle]:
	search array from m+1 to n-1;
```

^4c30d1

Notice that we have called the function in its own definition, this is called [[Recursion]].
==The [[Running time|Run-time]] order of binary search is given by $O(log(n))$ and $\Omega(1)$.==