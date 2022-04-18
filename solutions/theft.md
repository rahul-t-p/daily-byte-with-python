> You are a thief trying to steal from houses in a neighborhood. The amount of money that can be stolen from the i<sup>th</sup> house is represented by `nums[i]`. While you'd like to steal from all the houses, if adjacent houses are broken into, the police are notified via a security system. Return the largest amount of money you can steal without alerting the police.
>
> Note: You may not modify `nums`.
>
> Ex: Given the following `nums`...
> - `nums = [1, 3, 2, 5, 2]`, return 8.

Solution:
```
def maximum_sum_of_alternate_numbers(nums):
    return max(sum(nums[::2]), sum(nums[1::2]))
```

Test results:
```
In [9]: maximum_sum_of_alternate_numbers([1, 3, 2, 5, 2])
Out[9]: 8
```