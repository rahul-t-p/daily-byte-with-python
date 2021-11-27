> This question is asked by Facebook. Given a linked list, containing unique values, reverse it, and return the result.
>
> Ex: Given the following linked lists...
> - 1->2->3->null, return a reference to the node that contains 3 which points to a list that looks like the following: 3->2->1->null
> - 7->15->9->2->null, return a reference to the node that contains 2 which points to a list that looks like the following: 2->9->15->7->null
> - 1->null, return a reference to the node that contains 1 which points to a list that looks like the following: 1->null

Solution:
```
class LinkedList:
    '''Singly linked list'''
    class _Node:
        '''singly linked node'''
        def __init__(self, element, nextNode=None):
            self._element = element
            self._nextNode = nextNode
    
    def __init__(self):
        self._head = None
        self._size = 0

    def __len__(self):
        '''returns the size of the linked list'''
        return self._size
    
    def printLinkedList(self):
        '''prints elements of the linked list'''
        printVal = self._head
        while(printVal is not None):
            print(printVal._element, end='->')
            printVal = printVal._nextNode
        print('null')
        
    def addNodeAtEnd(self, newElement):
        '''adds a new node at the end of the linked list'''
        newNode = self._Node(newElement)
        self._size += 1
        if self._head is None:
            self._head = newNode
            return
        traverseNode = self._head
        while(traverseNode._nextNode):
            traverseNode = traverseNode._nextNode
        traverseNode._nextNode = newNode
    
    def reverse_list(self):
        '''reverse the linked list'''
        prevNode, nextNode = None, None
        currentNode = self._head
        while(currentNode is not None):
            nextNode = currentNode._nextNode
            currentNode._nextNode = prevNode
            prevNode = currentNode
            currentNode = nextNode
        self._head = prevNode
```

Test results:
```
In [2]: List1 = LinkedList()
   ...: for i in [1, 2, 3]: List1.addNodeAtEnd(i)
   ...: List1.printLinkedList()
1->2->3->null

In [3]: List1.reverse_list()
   ...: List1.printLinkedList()
3->2->1->null

In [4]: 

In [4]: List2 = LinkedList()
   ...: for i in [7, 15, 9, 2]: List2.addNodeAtEnd(i)
   ...: List2.printLinkedList()
7->15->9->2->null

In [5]: List2.reverse_list()
   ...: List2.printLinkedList()
2->9->15->7->null

In [6]: 

In [6]: List3 = LinkedList()
   ...: for i in [1]: List3.addNodeAtEnd(i)
   ...: List3.printLinkedList()
1->null

In [7]: List3.reverse_list()
   ...: List3.printLinkedList()
1->null
```

References:
1. [Python Program to Reverse a linked list](https://www.geeksforgeeks.org/python-program-for-reverse-a-linked-list/)