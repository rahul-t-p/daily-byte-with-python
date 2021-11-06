> Design a class to implement a stack using only a single queue. Your class, QueueStack, should support the following stack methods: push() (adding an item), pop() (removing an item), peek() (returning the top value without removing it), and empty() (whether or not the stack is empty).

Solution:
```
class QueueStack:
    '''FIFO queue implementation based on Python list as underlying storage'''

    def __init__(self):
        '''Create an empty queue'''
        self._data = []
        self._size = 0

    def push(self, e):
        '''Adding an element e'''
        self._data.insert(0, e)
        self._size += 1

    def pop(self):
        '''Removing an element'''
        self._data.pop()
        self._size -= 1

    def empty(self):
        '''Return whether or not the stack is empty'''
        return self._size == 0

    def peek(self):
        '''Return the top value'''
        if self.empty():
            raise Exception('Queue is empty')
        return self._data[-1]
```

Test results:
```
In [38]: Q = QueueStack()

In [39]: Q.empty()
Out[39]: True

In [40]: Q.peek()
---------------------------------------------------------------------------
Exception                                 Traceback (most recent call last)
<ipython-input-40-b169da0e2470> in <module>
----> 1 Q.peek()

<ipython-input-37-056f0ede1d4d> in peek(self)
     24         '''Return the top value'''
     25         if self.empty():
---> 26             raise Exception('Queue is empty')
     27         return self._data[-1]
     28 

Exception: Queue is empty

In [41]: Q.push(10)

In [42]: Q.push(6)

In [43]: Q.push(7)

In [44]: Q.push(3)

In [45]: Q.empty()
Out[45]: False

In [46]: Q.peek()
Out[46]: 10

In [47]: Q.pop()

In [48]: Q.peek()
Out[48]: 6
```
