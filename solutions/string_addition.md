> Given two non-negative numbers, `num1` and `num2` represented as strings, sum the integers together and return the result as a string.
>
> Ex: Given the following values for `num1` and `num2`...
> - `num1` = "2", `num2` = "5", return "7".
> - `num1` = "7", `num2` = "95", return "102".

Solution:
```
def string_addition(num1, num2):
    return str(int(num1) + int(num2))
```

Test results:
```
In [2]: string_addition("2", "5")
Out[2]: '7'

In [3]: string_addition("7", "95")
Out[3]: '102'
```