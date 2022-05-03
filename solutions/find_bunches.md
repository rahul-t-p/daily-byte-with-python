> Given a string `S` that contains only lowercase letters, return a list containing the intervals of all the bunches. A bunch is a set of contiguous characters (larger than two) that are all the same. An interval that represents a bunch contains the starting index of the bunch and the ending index of the bunch.
>
> Note: The intervals returned should be in ascending order according to start indexes.
>
> Ex: Given the following `S`...
> - `S = "aaabbbccc"`, return [[0,2],[3,5],[6,8]].
> - `S = "aaabbcddddd"`, return [[0,2],[6,10]].

Solution:
```
def find_bunches(S):
    bunches = list()
    buf = None
    start_idx = end_idx = 0
    for idx in range(len(S)):
        if (buf is None) or (buf != S[idx]):
            buf = S[idx]
            if end_idx - start_idx > 1:
                bunches.append([start_idx, end_idx])
            start_idx = end_idx = idx
        elif buf == S[idx]:
            end_idx += 1
            if (idx == len(S)-1) and (end_idx - start_idx > 1):
                bunches.append([start_idx, end_idx])
    return bunches
```

Test results:
```
In [5]: find_bunches("aaabbbccc")
Out[5]: [[0, 2], [3, 5], [6, 8]]

In [6]: find_bunches("aaabbcddddd")
Out[6]: [[0, 2], [6, 10]]
```
