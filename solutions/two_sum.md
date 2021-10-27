> This question is asked by Google. Given an array of integers, return whether or not two numbers sum to a given target, k.
>
> Note: you may not sum a number with itself.
>
> Ex: Fiven the following...
> - [1, 3, 8, 2], k = 10, return true (8+2)
> - [3, 9, 13, 7], k = 8, return false
> - [4, 2, 6, 5, 2], k = 4, return true (2+2)

Solution-1:
```
def two_sum(number_list, k):
    for i in range(len(number_list)):
        for j in range(i+1, len(number_list)):
            two_sum = number_list[i] + number_list [j]
            if two_sum == k:
                return True
    return False
```

Solution-2:
```
def two_sum(number_list, k):
    for i in range(len(number_list)):
        if (k-number_list[i]) in number_list[i+1:]:
            return True
    return False
```

Test results:
```
In [18]: two_sum([1, 3, 8, 2], 10)
Out[18]: True

In [19]: two_sum([3, 9, 13, 7], 8)
Out[19]: False

In [20]: two_sum([4, 2, 6, 5, 2], 4)
Out[20]: True
```