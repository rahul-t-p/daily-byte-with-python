> This question is asked by Google. Given a linked list and a value, remove all nodes containing the provided value, and return the resulting list.
>
> Ex: Given the following linked lists and values...
> - 1->2->3->null, value = 3, return 1->2->null
> - 8->1->->1->4->12->null, value = 1, return 8->4->12->null
> - 7->12->2->9->null, value = 7, return 12->2->9->null

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
    
    def removeValue(self, val):
        '''removes all nodes containing the value; val'''
        # return if the linked list is empty
        if(self._head is None): return
        
        # remove val from the starting and update the head value
        while(self._head._element == val):
            self._head = self._head._nextNode
            self._size -= 1
            if(self._head is None): return # if the resulting linked list is empty return
        
        # pointers for traversing the linked list, prevTraverseNode will be used to back up traverseNode's previous Node
        traverseNode = self._head
        prevTraverseNode = self._head
        
        # traverse through the linked list
        while(traverseNode._nextNode):
            traverseNode = traverseNode._nextNode
            if(traverseNode._element == val): # if the node value matches val, link previos Node and next Node
                prevTraverseNode._nextNode = traverseNode._nextNode
                self._size -= 1
            else:
                prevTraverseNode = prevTraverseNode._nextNode
```

Test results:
```
In [4]: L_list = LinkedList()
   ...: for i in [1, 2, 3]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->2->3->null

In [5]: L_list.removeValue(3)
   ...: L_list.printLinkedList()
1->2->null

In [6]: 

In [6]: L_list = LinkedList()
   ...: for i in [8, 1, 1, 4, 12]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
8->1->1->4->12->null

In [7]: L_list.removeValue(1)
   ...: L_list.printLinkedList()
8->4->12->null

In [8]: 

In [8]: L_list = LinkedList()
   ...: for i in [7, 12, 2, 9]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
7->12->2->9->null

In [9]: L_list.removeValue(7)
   ...: L_list.printLinkedList()
12->2->9->null
```