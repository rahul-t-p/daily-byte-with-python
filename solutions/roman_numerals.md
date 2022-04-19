> Given a string `s`, that represents a Roman numeral, return its associated integer value.
>
> Note: You may assume that each string represents a valid Roman numeral and its value will not exceed one thousand.
>
> Ex: Given the following string `s`...
> - `s = "DCLII"`, return 652.
> - `s = "VIII"`, return 8.

Solution:
```
roman_to_integer_map = {"I" : 1, "V": 5, "X" : 10, "L" : 50, "C" : 100, "D" : 500, "M" : 1000}

def roman_to_integer(s):
    int_val = 0
    for i in s:
        int_val += roman_to_integer_map[i]
    return int_val
```

Test results:
```
In [3]: roman_to_integer("DCLII")
Out[3]: 652

In [4]: roman_to_integer("VIII")
Out[4]: 8
```