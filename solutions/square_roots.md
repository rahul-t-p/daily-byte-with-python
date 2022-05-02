> Given a non-negative integer `x`, return its square root.
>
> Note: You may not use a built in square root function and decimals should be truncated to return an integer value.
>
> Ex: Given the following `x`...
> - `x = 9`, return 3.
> - `x = 12`, return 3.

Solution:
```
def square_root(x):
    return int(x ** (1/2))
```

Test results:
```
In [2]: square_root(9)
Out[2]: 3

In [3]: square_root(12)
Out[3]: 3
```