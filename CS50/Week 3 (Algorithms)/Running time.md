Rather than being ultra-specific about mathematical terms, computer scientists discuss efficiency in the *order of* various running times.

Running time involves analysis using the big O notation. Take a look at the following graph
![[Pasted image 20240704180230.png]]
The running time of al1(algorithm1) is O(n) or order of n where n is the size of the problem, the second is O(n) as well and for al3 it is o(logn).

Some common running times we may see are:
- $O(n)$
- $O(n^2)$
- $O(nlog(n))$
- $O(log(n))$
- $O(1)$
 
Of the running times above $O(n^2)$ is considered the worst and $O(1)$ is the fastest.

[[Search Algorithms#^81a9de|Linear Search]] was of the order $O(n)$ because it would take order $n$ in the worst case to run, while [[Search Algorithms#^45a3ac|Binary Search]] was of $O(log(n))$ because it would take fewer or fewer steps to run even in the worst case.

We are concerned with the best and worst case scenarios 
$\Omega()$ is used to denote best case scenario.
In cases where both best case and worst case scenarios are same we use $\Theta()$. 