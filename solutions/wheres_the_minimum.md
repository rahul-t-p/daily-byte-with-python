> Given an sorted integer array, `nums`, that has been rotated at an unknown index, return the minimum value.
>
> Note: The array only contains unique values.
>
> Ex: Given the following array `nums`...
> - nums = [7, 9, 10, 2, 4, 6], return 2.

Solution-1:
```
def find_min(nums):
    return min(nums)
```

Solution-2:
```
def find_min(nums):
    min_ = float('inf')
    for i in nums:
        if i < min_: min_ = i
    return min_
```

Test results:
```
In [4]: find_min([7, 9, 10, 2, 4, 6])
Out[4]: 2
```