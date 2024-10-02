#Trees
Basically, a tree is a **non** linear and hierarchical data structure with a collection of nodes \
Each node stores a value and a reference to another node



# Binary Tree
#binary-Trees , #Trees , #data-struct
A node x, is going to have a parent, an left and right child, and an item\
The root node is the very top node, it lacks any parents\
A tree will decompose into sub trees. The new root being the highest piece, imaging it with no parents and obv no siblings\
	Consists of node x and it's decendants, where x is the new root
- Depth(x):
	- n of edges in path from x up to root
- Height(x):
	- n of edges in the longest downward path from root from x
	- Max depth of node in x subtree
Leaves are nodes with 0 children\ 
- All leaves have height 0 
Always drawn downwards\
A tree will have a height(x)\
* Full binary Tree
	* Special type of binary tree where every parent node has either two or zero children
	* Also known as proper binary Tree
* Complete Binary Tree
	* Special type of Binary Tree where all levels of tree are completely filled except lowest nodes which are filled from the left as much as possible 
* Balanced Tree
	* Also known as height-balanced
	* The left and right subtree of any node differ by not more than one
	* An Unbalanced Tree is one that isn't balanced 
## Traversal\
```Python
TreeWalk(x):
	if x not None:
		TreeWalk(x.left)
		print x.key
		Treewalk(x.right)
```
x is the root, will basically print bottom to up and print left part of the tree before left
O(n) time
##### Operations
* subtree.first(node):
	* Trying to locate the first item in traversal
	* This would be the left most leaf
	* So just keep making node node.left until node.left is None, then node is the first
	* Will take O(Depth(first node)) so O(h) where h is the height of the entire tree 
* Successor(node)
	* O(h)
	* next after node in tree's traversal order 
	* If node has a right child, return subtree.first of said right node 
	* else: walk up itree(node = node.parent) 
		* until go up a left branch (node == node.parent.left) 
	* return node
## Insertion/Deletion
- Subtree.insert.after(node,new):
	- Want to insert new right after node
	- If inserting before and there's no left child, stick it there
	- If insering after and there's no right child, stick it there
		- Set node.right to new, new's parents have to be node
	- If inserting after and there is a right child, new will be the left child of the succesor of node
	- O(h) time
- Subtree.delete(node):
	- Deleting a leaf, just... get rid of it, remove pointer from parent to it
	- When deleting somehting not a leaf, swap with the predeseccor until becomes a leaf,  then delete leaf
	- Moving items of nodes instead of nodes themselves
	- if node is leaf: 
		- detach from parent
	- else :
		- if node.left: 
			- Swap node :item with predecessors(node) .item 
			* Subtree. Delete(predecessor)
### Sequence and set
Seq:\
	traversal order is going to be it's order\
	
Set:\ 
	traversal order = increasing item key\
	Basically a Binary search Tree
	- left nodes are less than parent and right nodes
	- parents are less than right nodes
	- right most leaf should be greatest value 
