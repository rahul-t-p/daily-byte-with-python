> Given a non-empty integer array, `nums`, return the minimum number of moves to make all values in `nums` equal. A move consists of incrementing all but one element in the array by one.
>
> Ex: Given the following `nums`...
> - `nums = [1, 2, 3]`, return 3. [1, 2, 3] -> [2, 3, 3] -> [3, 4, 3] -> [4, 4, 4].

Solution:
```
def count_to_equalize(nums):
    count = 0
    nums_buf = nums.copy()

    while len(set(nums_buf)) != 1:
        nums_buf = list(map(lambda x: x+1, nums_buf))
        nums_buf[nums_buf.index(max(nums_buf))] -= 1
        count += 1

    return count
```

Test results:
```
In [7]: count_to_equalize([1, 2, 3])
Out[7]: 3
```
