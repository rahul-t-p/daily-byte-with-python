> This question is asked by Microsoft. Given a linked list, containing unique numbers, return whether or not it has a cycle.
>
> Note: a cycle is a circular arrangement (i.e. one node points back to a previous node)
>
> Ex: Given the following linked lists...
> - 1->2->3->1, return true (3 points back to 1)
> - 1->2->3, return false
> - 1->1, return true (1 point back to itself)

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


class CircularLinkedList:
    '''Circularly linked list'''
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
        while(printVal._nextNode != self._head):
            print(printVal._element, end='->')
            printVal = printVal._nextNode
        print(printVal._element, end='->')
        print(printVal._nextNode._element)
        
    def addNode(self, newElement):
        '''adds a new node at the end of the linked list'''
        newNode = self._Node(newElement)
        self._size += 1
        if self._head is None:
            self._head = newNode
            self._head._nextNode = self._head
            return
        traverseNode = self._head
        while(traverseNode._nextNode != self._head):
            traverseNode = traverseNode._nextNode
        newNode._nextNode = self._head
        traverseNode._nextNode = newNode


def contains_cycle(linked_list):
    traverseNode = linked_list._head
    while((traverseNode._nextNode is not None) and (traverseNode._nextNode != linked_list._head)):
        traverseNode = traverseNode._nextNode
    return traverseNode._nextNode == linked_list._head
```

Test results:
```
In [4]: List1 = CircularLinkedList()
   ...: for i in [1, 2, 3]: List1.addNode(i)
   ...: List1.printLinkedList()
1->2->3->1

In [5]: List2 = LinkedList()
   ...: for i in [1, 2, 3]: List2.addNodeAtEnd(i)
   ...: List2.printLinkedList()
1->2->3->null

In [6]: List3 = CircularLinkedList()
   ...: for i in [1]: List3.addNode(i)
   ...: List3.printLinkedList()
1->1

In [7]: 

In [7]: contains_cycle(List1)
Out[7]: True

In [8]: contains_cycle(List2)
Out[8]: False

In [9]: contains_cycle(List3)
Out[9]: True
```

References:
1. [Python Circular Linked List Program](https://www.tutorialspoint.com/python-circular-linked-list-program)