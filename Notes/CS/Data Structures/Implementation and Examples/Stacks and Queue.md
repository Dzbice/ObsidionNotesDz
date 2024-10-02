Array interpretation
```Python
class Stack: 
	def __init__(self):
		self.data = []
	def push(self,node):
		self.data.append(node)
	def pop(self):
		self.data.pop()
```
Deque
```Python
from collections import deque
stack = deque()
stack.append('a')
stack.pop()
```

Queue
List interpretation
```Python
q = []
q.insert(0,12) #insert specifices position, so first thing is pushed to last
q.insert(0,43)
q.insert(0,431)
q.pop()#removes 12
```
Deque
```Python
from collection import deque
q = deque()
q.appendleft(5)
q.appendleft(4)
q.append(43)
q.pop() # removes 5
```