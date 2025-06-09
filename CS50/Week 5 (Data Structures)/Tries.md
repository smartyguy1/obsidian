- Tries combine structures and pointers together to store data in an interesting way.
- The data to be searched for in the trie is now a roadmap.
	- If we can reach a destination, the data exists.
	- If you can't it doesn't.
- Unlike hash tables, there is no room for collisions and no two pieces of data (unless they are identical) have the same path.
- In a trie, the paths form a central **root** note to a **leaf** node.
Example: A trie that leads to the University name with the year that it was founded in:
![[Pasted image 20240828101756.png]]