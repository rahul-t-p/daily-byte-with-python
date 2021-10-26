> This question is asked by Google. Given a string, reverse all of its characters and return the resulting string.
>
> Ex: Given the following strings...
> - "Cat", return "taC"
> - "The Daily Byte", return "etyB yliaD ehT"
> - "civic", return "civic"

Solution:
```
def reverse_string(string):
    return string[::-1]
```

Test results:
```
In [7]: reverse_string("Cat")
Out[7]: 'taC'

In [6]: reverse_string("The Daily Byte")
Out[6]: 'etyB yliaD ehT'

In [8]: reverse_string("civic")
Out[8]: 'civic'
```