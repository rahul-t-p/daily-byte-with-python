> This question is asked by Apple. Given two binary strings (strings containing only 1s and 0s) return their sum (also as a binary string).
>
> Note: neither binary string will contain leading 0s unless the string itself is 0
>
> Ex: Given the following binary strings...
> - "100" + "1", return "101"
> - "11" + "1", return "100"
> - "1" + "0", return "1"

Solution:
```
def add_binary(n1, n2):
    return bin(int(n1, 2)+int(n2,2))
```

Test results:
```
In [24]: add_binary("100", "1")
Out[24]: '0b101'

In [25]: add_binary("11", "1")
Out[25]: '0b100'

In [26]: add_binary("1", "0")
Out[26]: '0b1'
```