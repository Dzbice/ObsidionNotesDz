```Python 
class Node: 
	def __init__(self, data = None, next = None):
		self.data = data
		self.next = next

class LinkList:
	def __init__(self):
		self.head = None
		
	def insertAtbeginning(self,data):
		node = Node(data,self.Head)
		self.head = node
		
	def insertAtend(self,data):
		if self.head is None:
			self.head = Node(data,None)
			return 
		itr = self.head
		while itr.next:
			itr = itr.next
		itr.next = Node(data,None)

	def printList(self):
		if self.head is None:
			print("list is empty)
			return
		itr = self.head
		llist = ""
		while itr:
			llist += str(itr) + "->"
			itr = itr.next
		print(llist)

	def listTollist(self,values:list):
		self.head = values[0]
		for i in values[1:]: 
			self.insertAtend(i)

	def listLen(self):
		count = 0 
		itr = self.head
		while itr:
			count += 1
			itr = itr.next
		return count

	def remove(self,index):
		if index < 0 or index >= self.listLen():
			raise Exception("Invalid Index")
		if index == 0:
			self.head = self.head.next
			return 

		while itr:
			if count == index -1:
				itr.next = itr.next.next
				break
			count += 1
			itr = itr.next

	def insert_at(self,index,value):
		if index < 0 or index >= self.listLen():
			raise Exception("Invalid Index")
		if index == 0:
			self.insertAtbeginning(value)
			return
		count = 0 
		itr = self.head
		while itr:
			if count == index - 1:
				node = Node(value,itr.next)
				itr.next = node
				break
			count += 1
			itr = itr.next
		
	
```