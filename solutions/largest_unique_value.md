> Given an integer array, `nums`, return the largest unque value in `nums`.
>
> Ex: Given the following `nums`...
> - `nums = [4, 9, 2, 9]`, return 4.
> - `nums = [8, 1, 10, 1, 4, 8, 4, 10]`, return -1.

Solution:
```
def largest_unique_value(nums):

    unique_values = list(filter(lambda x: nums.count(x) == 1, nums))
    
    return -1 if unique_values == [] else max(unique_values)
```

Test results:
```
In [4]: largest_unique_value([4, 9, 2, 9])
Out[4]: 4

In [5]: largest_unique_value([8, 1, 10, 1, 4, 8, 4, 10])
Out[5]: -1
```