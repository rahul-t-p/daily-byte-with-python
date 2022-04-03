> Given a list of `nums` and a `target`, return all the unique combinations of `nums` that sum to `target`.
>
> Ex: Given the following nums and target...
> - nums = [8, 2, 2, 4, 5, 6, 3]
>   
>   target = 9
>   
>   return [[2,2,5],[2,3,4],[3,6],[4,5]].

Solution:
```
from itertools import combinations, permutations

def sum_to_target(nums, target):
    nums_combinations = list()
    target_combinations = list()

    # Find all combinations of nums
    for n in range(len(nums) + 1):
        nums_combinations += list(combinations(nums, n))
    # Filter combinations sums to target
    for combination in nums_combinations:
        if sum(combination) == target:
            target_combinations.append(combination)
    # Filter unique combinations
    target_combinations = list(set(target_combinations))
    for combination in target_combinations:
        for permutation in list(permutations(combination)):
            if((permutation in target_combinations) and (permutation != combination)):
                target_combinations.remove(permutation)

    return target_combinations
```

Test results:
```
In [25]: nums = [8, 2, 2, 4, 5, 6, 3]
    ...: target = 9

In [26]: sum_to_target(nums, target)
Out[26]: [(2, 2, 5), (4, 5), (6, 3), (2, 4, 3)]

```
