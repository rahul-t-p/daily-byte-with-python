> Given a sorted integer array `nums` and a `target`, search for the target with in the array. If the target exists within the array, return it's index. If it does not exist within the array, return `-1`.
>
> Ex: Given the following `nums` and `target`...
> - `nums = [-5, -3, 0, 3, 8, 12, 40]`, `target = 8`, return `4`.
> - `nums = [1, 2, 3, 6, 8]`, `target = 10`, return `-1`.

Solution:
```
def find_value(nums, target):
    index = -1
    try:
        index = nums.index(target)
    except ValueError:
        index = -1
    return index
```

Test results:
```
In [7]: find_value([-5, -3, 0, 3, 8, 12, 40], 8)
Out[7]: 4

In [8]: find_value([1, 2, 3, 6, 8], 10)
Out[8]: -1
```