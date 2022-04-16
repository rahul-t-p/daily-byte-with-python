> Given a non-negative integer, `num`, repeatedly add all its digits until it has a single digit remaining and return it.
>
> Ex: Given the following `num`...
> - `num = 123`, return 6 (1 + 2 + 3 = 6).
> - `num = 8353`, return 1 (8 + 3 + 5 + 3 = 19 = 1 + 9 = 10 = 1 + 0 = 1).

Solution:
```
from functools import reduce

def final_digit(num):
    num_str = str(num)
    if len(num_str) == 1:
        return num
    sum_ = reduce(lambda x, y: int(x)+int(y), num_str)
    return final_digit(sum_)
```

Test results:
```
In [4]: final_digit(123)
Out[4]: 6

In [5]: final_digit(8353)
Out[5]: 1
```
