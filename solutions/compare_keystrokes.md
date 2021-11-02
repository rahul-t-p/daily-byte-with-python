> This question is asked by Amazon. Given two strings `s` and `t`, which represents a sequence of keystrokes, where `#` denotes a backspace, return whether or not the sequences produce the same result.
> 
> Ex: Given the following strings...
> - s = "ABC#", t = "CD##AB", return true
> - s = "como#pur#ter", t = "computer", return true
> - s = "cof#dim#ng", t = "code", return false

Solution:
```
def clean_up_string(string):
    stack = []
    for c in string:
        if c == '#':
            if stack == []: continue
            stack.pop()
        else:
            stack.append(c)
    return ''.join(stack)

def compare_keystrokes(s, t):
    return clean_up_string(s) == clean_up_string(t)
```

Test results:
```
In [15]: compare_keystrokes("ABC#", "CD##AB")
Out[15]: True

In [16]: compare_keystrokes("como#pur#ter", "computer")
Out[16]: True

In [17]: compare_keystrokes("cof#dim#ng", "code")
Out[17]: False
```