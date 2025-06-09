- Data structures are essentially, forms of organization in memory
- There are many ways to organize data in memory
- *Abstract data structures* are those that we can conceptually imagine. 

# Declaring structures:
```C
// This defines a structure that is in C, is called struct car.
// Note that whenever we want to declare this strucure we need to write "struct car" everytime
struct car
{
	int year;
	char model[10];
	char plate[7];
	int odometer;
	double engine_size;
};

// We can access the various fields by using the dot(.) operator

struct car mycar; // variable declaration

mycar.year =  2011;
strcpy(mycar.plate, "CS50");
mycar.odometer = 50505;

```

We sometimes require Data Structures to be able to utilize Dynamic Memory Allocation. We can do this by:
```C

struct car *mycar = malloc(sizeof(struct car)); // Variable Declaration

// field accessing
(*mycar).year = 2011;
strcpy((*mycar).plate, "CS50");
(*mycar).odometer = 50505;

// Using the above operators can get a bit tedious. However, there is a special operator that we can use to do field accessing. We use (->) operator, it dereferences the pointer on the LHS and access the field on the RHS.

mycar->year = 2011;
strcpy(mycar->plate, "CS50");
mycar->odometer = 50505;

```

There are four different types of Data Structures we are going to study:
- [[Arrays]]
- [[Linked lists]]
- [[Hash tables]] ^e44b11
- [[Tries]]

There are also some variations of these data types

# Pros and Cons of different Data types:

### Arrays:
- **Insertion is bad:** lots of shifting to fit an element in the middle.
- **Deletion is bad:** lost of shifting after removing an element
- **Lookup is great:** Random access and constant time
- **Relatively easy to sort**
- **Relatively small** size-wise
- Stuck with fixed size, **no flexibility**

### Linked lists
- **Insertion is easy:** Just attach at the front
- **Deletion is easy**(Once you find the element)
- **Lookup is bad:** We have to rely on Linear Search
- **Relatively difficult to sort:** Unless you're willing to compromise on super-fast insertion and instead sort as you construct
- **Relatively small size-wise**(not as small as arrays)

### Hash Tables
-  **Insertion is a two-step process:** Hash and then add.
- **Deletion is easy:** Once you find the element.
- **Lookup** is on average **better than with linked lists** because you have the benefit of a real-world constant factor.
- **Not an ideal data structure** if **sorting** is the goal.
- Can run a whole range or series of data.

### Tables:
- **Insertion is complex**: a lot of dynamic memory allocation. But this gets easier as you go.
- **Deletion is easy**: Just free a node.
- **Lookup is fast**: Not quite as fast as an array, but almost.
- **Already sorted:** Sorts as you build in almost all situation.
- **Rapidly becomes huge**: Even with very little data present. This is not great if space is at a premium.

