> This question is asked by Microsoft. Given a string, return the index of its first unique character. If a unique character does not exist, return `-1`.
>
> Ex: Given the following strings...
> - "abcabd", return 2
> - "thedailybyte", return 1
> - "developer", return 0

Solution:
```
def first_unique_char(string):
    ret = -1
    for i in range(len(string)):
        if string[i] not in string[:i]+string[i+1:]:
            ret = i
            break
    return ret
```

Test results:
```
In [6]: first_unique_char("abcabd")
Out[6]: 2

In [7]: first_unique_char("thedailybyte")
Out[7]: 1

In [8]: first_unique_char("developer")
Out[8]: 0
```