> This question is asked by Facebook. Given two strings `s` and `t` return whether or not `s` is ana anagram of `t`.
>
> Note: An anagram is a word formed by reordering the letters of another word.
>
> Ex: Givne the following strings...
> - s = "cat", t = "tac", return true
> - s = "listen", t = "silent", return true
> - s = "program", t = "function", return false

Solution:
```
def valid_anagram(s, t):
    return sorted(list(s))==sorted(list(t))
```

Test results:
```
In [40]: valid_anagram("cat", "tac")
Out[40]: True

In [41]: valid_anagram("listen", "silent")
Out[41]: True

In [42]: valid_anagram("program", "function")
Out[42]: False
```