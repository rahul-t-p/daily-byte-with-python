> Given two integer arrays, `nums1` and `nums2`, return the intersection of the two arrays(i.e. the elements they have in common).
>
> Ex: Given the following `nums1` and `nums2`...
> - `nums1 = [1, 2, 2, 3]`, `nums2 = [0, 2, 2, 5]`, return [2, 2].

Solution:
```
def common_values(nums1, nums2):
    nums2_tmp = nums2.copy()
    common_vals = []
    for i in nums1:
        if i in nums2_tmp:
            nums2_tmp.remove(i)
            common_vals.append(i)
    return common_vals
```

Test results:
```
In [2]: common_values([1, 2, 2, 3], [0, 2, 2, 5])
Out[2]: [2, 2]
```