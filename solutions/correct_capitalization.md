> This question is asked by Google. Given a string, return whether or not it uses capitalization correctley. A string correctly uses capitalization if all letters are capitalized, no letters are capitalized or only the first letter is capitalized.
>
> Ex: Given the following strings...
> - "USA" ,  return true
> - "Calvin", return true
> - "compUter", return false
> - "coding", return true

Solution:
```
def correct_capitalization(string):
    return True if string.istitle() or string.islower() or string.isupper() else False
```

Test results:
```
In [18]: correct_capitalization("USA")
Out[18]: True

In [19]: correct_capitalization("Calvin")
Out[19]: True

In [20]: correct_capitalization("compUter")
Out[20]: False

In [21]: correct_capitalization("coding")
Out[21]: True
```