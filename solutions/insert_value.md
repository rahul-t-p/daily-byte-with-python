> Given a sorted array of integers, `nums`, and a `target`, return the index of the `target` within `nums`. If it does not exist, return the index of where `target` should be inserted.
>
> Ex: Given the following `nums` and `target`...
> - `nums = [1, 5, 8, 12]`, `target = 12`, return 3.
> - `nums = [3, 4, 7, 12, 29]`, `target = 5`, return 2.

Solution:
```
def insert_value(nums, target):

    for i in range(len(nums)):
        if nums[i] == target:
            return i
        elif nums[i] > target:
            return i
    
    return len(nums)
```

Test results:
```
In [2]: insert_value([1, 5, 8, 12], 12)
Out[2]: 3

In [3]: insert_value([3, 4, 7, 12, 29], 5)
Out[3]: 2
```