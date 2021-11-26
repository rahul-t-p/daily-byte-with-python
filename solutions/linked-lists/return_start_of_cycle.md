> This question is asked by Apple. Given a potentially cyclical linked list where each value is unique, return the node at which the cycle starts. If the list does not contain a cycle, return `null`.
>
> Ex: Given the following linked lists...
> - 1->2->3, return null
> - 1->2->3->4->5->2 (5 points back to 2), return a reference to the node containing 2
> - 1->9->3->7->7 (7 points back to itself), return a reference to the node containing 7

Solution:
```
class Node:
    def __init__(self, element, nextNode=None):
        self._element = element
        self._nextNode = nextNode


class LinkedList:
    def __init__(self):
        self._head = None
    def printLinkedList(self):
        unique_elements = []
        traverseNode = self._head
        while((traverseNode is not None)):
            print(traverseNode._element, end='->')
            if traverseNode._element in unique_elements:
                break
            unique_elements.append(traverseNode._element)
            traverseNode = traverseNode._nextNode


def start_of_cycle(linked_list):
    '''
    returns the node at which the cycle starts
    If the list does not contain a cycle, returns None
    '''
    ret = LinkedList()
    unique_elements = []
    traverseNode = linked_list._head
    while((traverseNode is not None)):
        if traverseNode._element in unique_elements:
            ret._head = traverseNode
            break
        unique_elements.append(traverseNode._element)
        traverseNode = traverseNode._nextNode
    return ret
```

Test results:
```
In [4]: List1 = LinkedList()
   ...: node1 = Node(1)
   ...: node2 = Node(2)
   ...: node3 = Node(3)
   ...: List1._head = node1
   ...: node1._nextNode = node2
   ...: node2._nextNode = node3
   ...: List1.printLinkedList()
1->2->3->
In [5]: C1 = start_of_cycle(List1)
   ...: C1.printLinkedList()

In [6]: 

In [6]: List2 = LinkedList()
   ...: node1 = Node(1)
   ...: node2 = Node(2)
   ...: node3 = Node(3)
   ...: node4 = Node(4)
   ...: node5 = Node(5)
   ...: List2._head = node1
   ...: node1._nextNode = node2
   ...: node2._nextNode = node3
   ...: node3._nextNode = node4
   ...: node4._nextNode = node5
   ...: node5._nextNode = node2
   ...: List2.printLinkedList()
1->2->3->4->5->2->
In [7]: C2 = start_of_cycle(List2)
   ...: C2.printLinkedList()
2->3->4->5->2->
In [8]: 

In [8]: List3 = LinkedList()
   ...: node1 = Node(1)
   ...: node2 = Node(9)
   ...: node3 = Node(3)
   ...: node4 = Node(7)
   ...: List3._head = node1
   ...: node1._nextNode = node2
   ...: node2._nextNode = node3
   ...: node3._nextNode = node4
   ...: node4._nextNode = node4
   ...: List3.printLinkedList()
1->9->3->7->7->
In [9]: C3 = start_of_cycle(List3)
   ...: C3.printLinkedList()
7->7->
```