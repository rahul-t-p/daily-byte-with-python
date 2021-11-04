> This question is asked by Google. Create a class CallCounter that tracks the number of calls a client has made within the last 3 seconds. Your class should contain one method, ping(int t) that receives the current timestamp (in milliseconds) of a new call being made and returns the number of calls made within the last 3 seconds.
>
> Note: you may assume that the time associated with each subsequent call to ping is strictly increasing.
>
> Ex: Given the following calls to ping…
> - ping(1), return 1 (1 call within the last 3 seconds)
> - ping(300), return 2 (2 calls within the last 3 seconds)
> - ping(3000), return 3 (3 calls within the last 3 seconds)
> - ping(3002), return 3 (3 calls within the last 3 seconds)
> - ping(7000), return 1 (1 call within the last 3 seconds)

Solution:
```
class CallCounter:
    def __init__(self):
        self.call_timestamps = []

    def ping(self, t):
        self.call_timestamps = [i for i in self.call_timestamps if i >= (t-3000)]
        self.call_timestamps.append(t)
        return len(self.call_timestamps)
```

Test results:
```
In [17]: counter = CallCounter()

In [18]: counter.ping(1)
Out[18]: 1

In [19]: counter.ping(300)
Out[19]: 2

In [20]: counter.ping(3000)
Out[20]: 3

In [21]: counter.ping(3002)
Out[21]: 3

In [22]: counter.ping(7000)
Out[22]: 1
```
