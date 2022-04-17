> You are given an array of integers, `nums`, that only contains values between one and `nums`.length (inclusive). Within `nums`, some values appear once and some values appear twice. Return a list containing all numbers between one and `nums.length` that are missing.
>
> Ex: Given the following `nums`...
> - `nums = [1, 2, 3, 3]`, return `[4]`.
> - `nums = [3, 2, 4, 1, 5]`, return `[]`.

Solution:
```
def missing_numbers(nums):
    return [i for i in range(1, len(nums)) if i not in nums]
```

Test results:
```
In [10]: missing_numbers([1, 2, 3, 3])
Out[10]: [4]

In [11]: missing_numbers([3, 2, 4, 1, 5])
Out[11]: []
```
