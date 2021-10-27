> This question is asked by Facebook. Given a string and the ability to delete at most one character, return whether or not it can form a palindrome.
>
> Note: a palindrome is a sequence of characters that reads the same forwards and backwards.
>
> Ex: Given the following strings...
> - "abcba", return true
> - "foobof", return true (remove the first 'o', the second 'o', or 'b')
> - "abccab", return false

Solution:
```
def valid_palindrome_with_removal(string):
    for idx in range(len(string)): # loop through the string
        buf = string[:idx]+string[idx+1:] # remove one character
        if buf == buf[::-1]: # check if the string is palindrome
            return True
    return False
```

Test results:
```
In [2]: valid_palindrome_with_removal("abcba")
Out[2]: True

In [3]: valid_palindrome_with_removal("foobof")
Out[3]: True

In [4]: valid_palindrome_with_removal("abccab")
Out[4]: False
```