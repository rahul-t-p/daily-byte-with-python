> Given an array of integes, `nums`, every value appears three times except one value which only appears once. Return the value that only appears once.
>
> Ex: Given the following array `nums`...
> - `nums = [1, 2, 2, 2, 3, 3, 3]`, return 1.
> - `nums = [3, 3, 2, 5, 2, 2, 5, 3, 9, 5]`, return 9.

Solution:
```
def one_value(nums):
    for i in set(nums):
        if nums.count(i) == 1:
            return i
    return -1
```

Test results:
```
In [2]: one_value([1, 2, 2, 2, 3, 3, 3])
Out[2]: 1

In [3]: one_value([3, 3, 2, 5, 2, 2, 5, 3, 9, 5])
Out[3]: 9
```