> Given an array of integers, `nums`, and a value `k`, return the number of continous subarrays that sum to `k`.
>
> Ex: Given the following `nums` and `k`...
> - `nums = [1, 1, 4]`, `k = 5`, return 1.
> - `nums = [3, 2, 2, 1, 1, 1]`, `k = 5`, return 3.

Solution - 1:
```
def continous_sum_to_target(nums, target):
    count = 0
    for idx_1 in range(len(nums)):
        for idx_2 in range(idx_1+1, len(nums)+1):
            if sum(nums[idx_1:idx_2]) == target:
                count += 1
    return count
```
Solution - 2:
```
def continous_sum_to_target(nums, target):
    count = 0
    for idx in range(len(nums)):
        tmp_target = target
        tmp_idx = idx
        while (tmp_target > 0) and (tmp_idx < len(nums)):
            print(nums[tmp_idx], tmp_idx)
            tmp_target -= nums[tmp_idx]
            tmp_idx += 1
            print(tmp_target)
            if tmp_target < 0: break
            elif tmp_target == 0: count += 1;
                
    return count
```

Test results:
```
In [2]: continous_sum_to_target([1, 1, 4], 5)
Out[2]: 1

In [3]: continous_sum_to_target([3, 2, 2, 1, 1, 1], 5)
Out[3]: 3
```