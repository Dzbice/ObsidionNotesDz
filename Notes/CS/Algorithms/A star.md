# A* 
- Searching method
- More efficient than Dijkstra
- shortest path

f(n) = g(n) + h(n)
The algorithm picks a node according to a value f: which is the sum of 2 parameters g and h. 
g - movement cost to move from the starting point to a given square on the grid
h - the estimated movement cost to move from that given square on the grid to the final destination
	h is often called the heuristic
```
1. Intiatialize Open list
2. Intialize closed list
	1. put starting node on open list(leave its f at 0)
3. while the open list isn't empty
	1. find the node with least f on open list, call it q
	2. pop q off open list
	3. generate q successors and set parents to q
	4. for each successor
		1. if successor is goal, stop
		2. else, find g and h for it. g = q.g + distance between successor and q. h = distance from goal to successor. 
		3. if node with same poisition as node is in open list which has a lowe f than successor, skip this one
		4. if node with same position as successor in closed list which has loswer f than successor, skip(otherwise add to open list) 
	5. end for loop
4. push q on closed list
5. endw(while loop)
```
approximate heurisitcs to calculate h
1. Manhattan Distance  #manhattan_distance 
	1. sum of abs() val of diff in goal x and y cords, and current cell x and y cords
	2. when to use? when movement only in 4 directions
2. diagonal distance
	1. maxumum of abs val diff in goal x and y cords and currecnt cell cords
	2. allowed to move in 8 directions
3. euclidean distance
	1. distance between current cell and goal cell using distance formula