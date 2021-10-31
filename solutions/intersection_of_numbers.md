> This question is asked by Google. Given two integer arrays, return their intersection.
>
> Note: the intersection is the set of elements that are common to both arrays.
>
> Ex: Given the following arrays...
> - nums1 = [2, 4, 4, 2], nums2 = [2, 4], return [2, 4]
> - nums1 = [1, 2, 3, 3], nums2 = [3, 3], return [3]
> - nums1 = [2, 4, 6, 8], nums2 = [1, 3, 5, 7], return []

Solution:
```
def intersection_of_num_lists(nums1, nums2):
    return list(set(nums1) & set(nums2))
```

Test results:
```
In [15]: intersection_of_num_lists([2, 4, 4, 2], [2, 4])
Out[15]: [2, 4]

In [16]: intersection_of_num_lists([1, 2, 3, 3], [3, 3])
Out[16]: [3]

In [17]: intersection_of_num_lists([2, 4, 6, 8], [1, 3, 5, 7])
Out[17]: []
```
