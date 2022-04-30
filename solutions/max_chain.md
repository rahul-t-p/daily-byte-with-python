> You are given `n` pairs of numbers and asked to form a chain. Two pairs of numbers can create a link in the chain if the second number in the first pair is less than the first number in the second pair. Return the length of the longest chain you can form.
>
> Note: You may use the pairs of numbers in any order and the first number in a pair is always less than the second number in a pair.
>
> Ex: Given the following pairs...
> - `pairs = [[3,4], [5, 6], [7, 8]]`, return 3.
> - `pairs = [[9, 14], [3, 5], [4, 7]]`, return 2.

Solution:
```
def max_chain(pairs):
    sorted_pairs = sorted(pairs)
    for idx in range(len(sorted_pairs)):
        if (idx < len(sorted_pairs)-1) and (sorted_pairs[idx][1] > sorted_pairs[idx+1][0]):
            sorted_pairs.remove(sorted_pairs[idx])
    return len(sorted_pairs)
```

Test results:
```
In [5]: max_chain([[3,4], [5, 6], [7, 8]])
Out[5]: 3

In [6]: max_chain([[9, 14], [3, 5], [4, 7]])
Out[6]: 2
```
