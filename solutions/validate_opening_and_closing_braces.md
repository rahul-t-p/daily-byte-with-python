> This question is asked by Gooble. Given a string only containing the flollowing characters `(`, `)`, `{`, `}`, `[`, and `]` return whether or not the opening and closing characters are in a valid order.
>
> Ex: Given the following strings...
> - "(){}[]", return true
> - "(({[]}))", return true
> - "{(})", return false

Solution:
```
def validate_opening_closing_braces(string):
    braces_map = {')':'(', '}':'{', ']':'['}
    stack = []
    for c in string:
        if c in '({[':
            stack.append(c)
        else:
            if stack == []: return False
            if stack.pop() != braces_map[c]: return False
    return stack == []
```

Test results:
```
In [6]: validate_opening_closing_braces("(){}[]")
Out[6]: True

In [7]: validate_opening_closing_braces("(({[]}))")
Out[7]: True

In [8]: validate_opening_closing_braces("{(})")
Out[8]: False
```