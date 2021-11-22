> This question is asked by Apple. Given two sorted linked lists, merge them together in ascending order and return a reference to the merged list.
>
> Ex: Given the followign lists...
> - list1 = 1->2->3, list2 = 4->5->6->null, return 1->2->3->4->5->6->null
> - list1 = 1->3->5, list2 = 2->4->6->null, return 1->2->3->4->5->6->null
> - list1 = 4->4->7, list2 = 1->5->6->null, return 1->4->4->5->6->7->null

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

def mergeLinkedLists(head1, head2):
    mergedList = LinkedList()

    while((list1._head) or (list2._head)):
        if(list1._head is None):
            mergedList.addNodeAtEnd(list2._head._element)
            list2._head = list2._head._nextNode
            continue
        if(list2._head is None):
            mergedList.addNodeAtEnd(list1._head._element)
            list1._head = list1._head._nextNode
            continue

        if (list1._head._element <= list2._head._element):
            mergedList.addNodeAtEnd(list1._head._element)
            list1._head = list1._head._nextNode
        else:
            mergedList.addNodeAtEnd(list2._head._element)
            list2._head = list2._head._nextNode
    return mergedList
```

Test results:
```
In [4]: list1 = LinkedList()
   ...: for i in [1, 2, 3]: list1.addNodeAtEnd(i)
   ...: list1.printLinkedList()
1->2->3->null

In [5]: list2 = LinkedList()
   ...: for i in [4, 5, 6]: list2.addNodeAtEnd(i)
   ...: list2.printLinkedList()
4->5->6->null

In [6]: list3 = mergeLinkedLists(list1, list2)
   ...: list3.printLinkedList()
1->2->3->4->5->6->null

In [7]: 

In [7]: list1 = LinkedList()
   ...: for i in [1, 3, 5]: list1.addNodeAtEnd(i)
   ...: list1.printLinkedList()
1->3->5->null

In [8]: list2 = LinkedList()
   ...: for i in [2, 4, 6]: list2.addNodeAtEnd(i)
   ...: list2.printLinkedList()
2->4->6->null

In [9]: list3 = mergeLinkedLists(list1, list2)
   ...: list3.printLinkedList()
1->2->3->4->5->6->null

In [10]: 

In [10]: list1 = LinkedList()
    ...: for i in [4, 4, 7]: list1.addNodeAtEnd(i)
    ...: list1.printLinkedList()
4->4->7->null

In [11]: list2 = LinkedList()
    ...: for i in [1, 5, 6]: list2.addNodeAtEnd(i)
    ...: list2.printLinkedList()
1->5->6->null

In [12]: list3 = mergeLinkedLists(list1, list2)
    ...: list3.printLinkedList()
1->4->4->5->6->7->null

```

References:
1. [Python - Linked Lists](https://www.tutorialspoint.com/python_data_structure/python_linked_lists.htm)