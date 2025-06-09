When a list is sorted it becomes much less taxing for the computer to search for an item. Recall that we can use [[Search Algorithms#^45a3ac|Binary Search]] on a sorted data-set not an unsorted one.

There are many such sorting algorithms.

# Selection Sort
We can represent the data in an array as follows:![[Pasted image 20240704190415.png]]
selection sort is very simple to implement
pseudocode:
```
for i from 0 to n-1:
	find smallest number between numbers[i] to numbers[n-1]
	swap smallest number with numbers[i]
```
To calculate the no. of steps, it took n-1 steps in the first loop then n-2 in 2nd loop so it can summarized as:
`(n-1) + (n-2) + ... + 1`
which is calculated as $\frac{n(n-1)}{2}$ steps. In the worst case it would take this many steps, so worst case order is $\Omega(n^2)$ however even if the list is sorted it would still run the whole loop again and have $O(n^2)$ since the worst and best case scenarios are the same ==we can denote the runtime order as $\Theta(n^2)$.==
# Bubble Sort
In bubble sort we essentially compare two values at a time and swap them in order. It is called bubble sort as the largest values in each iteration will seem to move back like a "bubble".
Pseudocode
```
Repeat n-1 times:
	for i from 0 to n-2:
		if numbers[i] and numbers[i+1] out of order :
			swap them;
	if no swaps quit;
```
The number of steps in this are also $\frac{n(n-1)}{2}$ . However, if the list is already sorted, it would run the loop once to check and then quit (since there were no swaps) so ==the worst case: $O(n^2)$ and the best case: $\Omega(n)$.==

# Merge Sort

We can use [[Recursion]] for sorting as well, in implementing **Merge Sort** Algorithm which is a very efficient algorithm.
The process is as follows:
>Divide the array in half
>Keep dividing each sub-array until left with one element
>Now work your way back merging the arrays back in a sorted manner

The pseudocode is as follows:
```
if only one number
	quit
else
	sort left half of number;
	sort right half of number;
	merge sorted halves
```

==The [[Running time|runtime]] of this algorithm is $\Theta(nlog(n))$==  
At large data-sets it would be faster then other arrays however this will come at the cost of memory, since we would have store larger data in temporary arrays. 