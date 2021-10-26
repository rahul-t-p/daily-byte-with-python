> This question is asked by Facebook. Given a string, return whether or not it forms a palindrome ignoring case and non-alphabetical characters.
> 
> Note: a palindrome is a sequence of characters that reads the same forwards and backwards.
>
> Ex: Given the following strings...
> - "level", return true
> - "algorithm", return false
> - "A man, a plan, a canal: Panama.", return true

Solution:
```
def valid_palindrome(string):
    string = ''.join(filter(str.isalpha, string)).lower()
    return True if string == string[::-1] else False
```

Test results:
```
In [2]: valid_palindrome("level")
Out[2]: True

In [3]: valid_palindrome("algorithm")
Out[3]: False

In [4]: valid_palindrome("A man, a plan, a canal: Panama.")
Out[4]: True
```