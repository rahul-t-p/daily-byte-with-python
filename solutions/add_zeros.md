> Given an array of integers, `nums`, duplicate the occurrence of each zero in the array by shifting other non-zero elements to the right.
>
Note: The modification to `nums` must be done in-place, do not return anything from your function, and elements beyond the length of the original array not not written.
>
> Ex: Given the following `nums`...
> - `nums = [1, 0, 4, 0, 5, 8]`, return null but `nums` should look as follows after your function runs [1,0,0,4,0,0].
> - `nums = [1, 4, 9]`, return null but `nums` should look as follows after your function runs [1, 4, 9].

Solution:
```
def add_zeros(nums):
    nums_len = len(nums)
    idx = 0
    while idx < nums_len:
        if nums[idx] == 0:
            nums.insert(idx+1, 0)
            idx += 1
        idx += 1
    nums[:] = nums[:nums_len]
```

Test results:
```
In [8]: nums = [1, 0, 4, 0, 5, 8]
   ...: add_zeros(nums)
   ...: nums
Out[8]: [1, 0, 0, 4, 0, 0]

In [9]: nums = [1, 4, 9]
   ...: add_zeros(nums)
   ...: nums
Out[9]: [1, 4, 9]
```
