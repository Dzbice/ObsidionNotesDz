### Arrays
#data-struct 
* Linear Data structure that holds and arranges elements
* Directly access element using an index, efficient
* 1D is fully linear while multi dimensional is a matrix
* An insertion is O(n) complexity since every thing could be swapped
	* Memory is allocated for the list, as you insert things, if you wish to insert into smth filled it swaps all other items below location in the list 1 space downwards
	* moving things up or down to stick item a into list
	* If arrays are full, then `len(A)*2` spaces are allocated and the list is copied down into that along with the new value
* Python lists are dynamic by default while tuples are static
### Linked Lists
#data-struct 
[[Linked List Implmentation]] 
- Tries to solve problems with array
- Stores things at random memory locations, with each element having a pointer to the next
	- Linking elements together, i.e. a linked list
- Insertion/Deletion at the beginning of the list is constant(O(1)) time
- In the middle/end is O(n)
- Accessing elements is O(n)
- **Benefits over array**
	1. Easier insertion,
	2. no need to pre allocate memory
#### Doubly linked list 
Points in both directions(prev and next point)
Allows for traversal in both directions

### Stacks
#data-struct 
[[Stacks and Queue]]
* Linear data structure that follows particular order where operations are performed
* LIFO(Last in, First Out) or FILO(First in Last Out)
* 3 main basic operations
	* Push: adds element
	* Pop: removes element from collect
	* Peet/Top: return top item without removing it
* Basically the element last added is the first to come off
* Possible application:
	* Back button on a browser 
	* Ctrl + Z uses stack to keep track of things
* Pusing/Popping is contant time, searching by value is O(n) complexity


### Queues
#data-struct 
[[Stacks and Queue]]
- Elements held in a sequence and access restricted to a single end
- Elements added(enqueed) at rear end and removed(dequeued) from the front
- FIFO data structure
- Python uses lists, and dequeue

### Hash Table
#data-struct 
- Specialized data structure that allows fast access to data based on a key
- Collisions happen if two different inputs have the same output, this can be dealt with in different ways
- Using a list to represent a hash table is O(n) complexity, compared to a dict which is O(1)
- Has key: value pairs
- ![[Pasted image 20240920190510.png]]


### balls
