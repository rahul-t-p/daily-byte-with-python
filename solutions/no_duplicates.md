> Given a sorted integer array, `nums`, remove duplicates from the array in-place such that each element only appears once. Once you've removed all the duplicates, return the length of the new array.
>
> Ex: Given the following `nums`...
> - `nums = [1, 2, 2, 4, 4, 6, 8, 8]`, return 5.
> - `nums = [1, 2, 3, 3]`, return 3.

Solution:
```
def unique_elements(nums):
    unique_elements = []
    for i in nums:
        if i not in unique_elements:
            unique_elements.append(i)
    return len(unique_elements)
```

Test results:
```
In [4]: unique_elements([1, 2, 2, 4, 4, 6, 8, 8])
Out[4]: 5

In [5]: unique_elements([1, 2, 3, 3])
Out[5]: 3
```
