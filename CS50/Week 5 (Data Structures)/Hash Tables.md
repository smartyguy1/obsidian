Hash tables combine the random access ability of an array with the dynamism of a linked list.

- Insertion can start to tend toward $\theta(1)$ 
- Deletion can start to tend toward $\theta(1)$
- Lookup can start to tend toward $\theta(1)$

We are gaining the advantages of both types of data structures, while mitigating the disadvantages.

There are certain [[CS50/Week 5 (Data Structures)/Data Structures#^e44b11|Pros and Cons]] associated with Hash Tables.

It is a combination of two things:
- A **Hash Function**: Returns a non-negative integer value called a *hash code*
- An **Array** capable of storing data of the type we wish to place into the data structure

>We run our data through the has function and then store it in the element of the array represented by the returned hash code.

# Hash Function:
 A good hash function should
- Use only the data being hashed
- Use all of the data being hashed
- Be deterministic
- Uniformly distribute data
- Generate very different hash codes for very similar data
#### Example:
```C
unsigned int hash(char* str)
{
	int sum = 0;
	for (int j = 0; str[j] != '\0'; j++)
	{
		sum += str[j];
	}
	return sum % HASH_MAX;
}
```

## Collision 
- A **collision** occurs when two pieces of data, when run through the hash function, yield the same hash code..
- We want to store *both* pieces of data in the hash table, so we cannot overwrite existing data.
- We need to find a way to get both the elements into the hash table while trying to preserve quick insertion and lookup.
### Resolving Collisions: Linear probing

- If we have a collision, we try to place the data in the next consecutive element in the array (wrapping around to the beginning if necessary) until we find a vacancy.
- This way we don't we don't need to look further than in the initial location to find it if we ever need to.
![[Pasted image 20240827114304.png]]

### Resolving Collisions: Chaining
- We could let each element of a hash table point to a [[Linked lists|linked list]]. This way multiple pieces of data can yield the same hash code and we'll be able to store it all.
- This way we've eliminated clustering.
- We know in case of linked list insertion has an order $O(1)$.
- For lookup, we only need to search through what is hopefully a small list, since we're distributing a large data into small lists.

![[Pasted image 20240827115211.png]]

