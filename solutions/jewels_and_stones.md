> This question is asked by Amazon. Given a string representing your stones and another string representing a list of jewels, return the number of stones that you have that are also jewels.
>
> Ex: Given the following jewels and stones...
> - jewels = "abc", stones = "ac", return 2
> - jewels = "Af", stones = "AaaddfFf", return 3
> - jewels = "AYOPD", stones = "ayopd", return 0

Solution:
```
def count_jewels(jewels, stones):
    count = 0
    for jewel in jewels:
        count += stones.count(jewel)
    return count
```

Test results:
```
In [22]: count_jewels("abc", "ac")
Out[22]: 2

In [23]: count_jewels("Af", "AaaddfFf")
Out[23]: 3

In [24]: count_jewels("AYOPD", "ayopd")
Out[24]: 0
```