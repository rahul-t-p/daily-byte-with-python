> This question is asked by Facebook. Given a string `s` containing only lowercase letters, continuously remove adjacent characters that are the same and return the result.
>
> Ex: Given the following strings...
> - s = "abccba", return ""
> - s = "foobar", return "fbar"
> - s = "abccbefggfe", return "a"

Solution:
```
def remove_adjacent_duplicates(s):
    stack = []
    for c in s:
        if (stack !=[]) and (c == stack[-1]):
            stack.pop()
        else:
            stack.append(c)
    if ''.join(stack) == s:
        return s
    
    return remove_adjacent_duplicates(''.join(stack))
```

Test results:
```
In [10]: remove_adjacent_duplicates("abccba")
Out[10]: ''

In [11]: remove_adjacent_duplicates("foobar")
Out[11]: 'fbar'

In [12]: remove_adjacent_duplicates("abccbefggfe")
Out[12]: 'a'
```