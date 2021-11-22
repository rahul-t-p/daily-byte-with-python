> This question is asked by Facebook. Given a linked list and a value `n`, remove the `nth` to last node and return the resulting list.
>
> Ex: Given the following linked lists...
> - 1->2->3->null, n = 1, return 1->2->null
> - 1->2->3->null, n = 2, return 1->3->null
> - 1->2->3->null, n = 3, return 2->3->null

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
        while printVal is not None:
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
        while (traverseNode._nextNode):
            traverseNode = traverseNode._nextNode
        traverseNode._nextNode = newNode
    
    def deleteNthToLastNode(self, n):
        '''removes Nth to last node'''
        if(n > self._size or n < 1):
            raise Exception('n is out of range')
        
        if(self._size == n):
            self._head = self._head._nextNode
            return
        
        traverseNode = self._head
        for i in range(self._size - n - 1):
            traverseNode = traverseNode._nextNode
        
        tmpNode = traverseNode._nextNode
        traverseNode._nextNode = tmpNode._nextNode
```

Test results:
```
In [7]: L_list = LinkedList()
   ...: for i in [1, 2, 3]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->2->3->null

In [8]: L_list.deleteNthToLastNode(1)
   ...: L_list.printLinkedList()
1->2->null

In [9]: 

In [9]: L_list = LinkedList()
   ...: for i in [1, 2, 3]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->2->3->null

In [10]: L_list.deleteNthToLastNode(2)
    ...: L_list.printLinkedList()
1->3->null

In [11]: 

In [11]: L_list = LinkedList()
    ...: for i in [1, 2, 3]: L_list.addNodeAtEnd(i)
    ...: L_list.printLinkedList()
1->2->3->null

In [12]: L_list.deleteNthToLastNode(3)
    ...: L_list.printLinkedList()
2->3->null

```