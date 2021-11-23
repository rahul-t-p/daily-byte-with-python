> This question is asked by Amazon. Given a non-empty linked list, return the middle node of the list. If the linked list contains an even number of elements, return the node closer to the end.
>
> Ex: Given the following linked lists...
> - 1->2->3->null, return 2
> - 1->2->3->4->null, return 3
> - 1->null, return 1

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

def find_middle_element(linked_list):
    '''returns the element of the middle node of the linked list'''
    middle_idx = round(linked_list._size // 2)
    traverseNode = linked_list._head
    for i in range(middle_idx):
        traverseNode = traverseNode._nextNode
    return traverseNode._element
```

Test results:
```
In [3]: L_list = LinkedList()
   ...: for i in [1, 2, 3]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->2->3->null

In [4]: find_middle_element(L_list)
Out[4]: 2

In [5]: 

In [5]: L_list = LinkedList()
   ...: for i in [1, 2, 3, 4]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->2->3->4->null

In [6]: find_middle_element(L_list)
Out[6]: 3

In [7]: 

In [7]: L_list = LinkedList()
   ...: for i in [1]: L_list.addNodeAtEnd(i)
   ...: L_list.printLinkedList()
1->null

In [8]: find_middle_element(L_list)
Out[8]: 1
```