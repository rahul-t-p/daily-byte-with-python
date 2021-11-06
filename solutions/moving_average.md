> This question is asked by Microsoft. Design a class, MovingAverage, which contains a method, next that is responsible for returning the moving average from a stream of integers.
>
> Note: a moving average is the average of a subset of data at a given point in time.
>
> Ex: Given the following series of events...
> - m = MovingAverage(3) # i.e. the moving average has a capacity of 3.
> - m.next(3) returns 3 because (3 / 1) = 3
> - m.next(5) returns 4 because (3 + 5) / 2 = 4
> - m.next(7) = returns 5 because (3 + 5 + 7) / 3 = 5
> - m.next(6) = returns 6 because (5 + 7 + 6) / 3 = 6

Solution:
```
class MovingAverage:
    def __init__(self, size=3):
        self.size = size
        self.data = []

    def next(self, val):
        if len(self.data) == self.size: self.data.pop()
        self.data.insert(0, val)
        return sum(self.data)/len(self.data)
```

Test results:
```
In [8]: m = MovingAverage(3)

In [9]: m.next(3)
Out[9]: 3.0

In [10]: m.next(5)
Out[10]: 4.0

In [11]: m.next(7)
Out[11]: 5.0

In [12]: m.next(6)
Out[12]: 6.0
```
