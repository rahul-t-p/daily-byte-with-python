> This question is asked by Microsoft. Given an array of strings, return the longest common prefix that is shared amongst all strings.
>
> Note: you may assume all strings only contain lowercase alphabetical characters.
>
> Ex: Given the following arrays...
> - ["colorado", "color", "cold"], return "col"
> - ["a", "b", "c"], return ""
> - ["spot", "spotty", "spotted"], return "spot"

Solution:
```
def longest_common_prefix(string_list):
    # extract substrings of the first string in the list
    sub_strings = []
    for i in range(len(string_list[0])+1):
        for j in range(i+1, len(string_list[0])+1):
            sub_strings.append(string_list[0][i:j])
    # sort the substrings based on its length (longest substring first)
    sub_strings = sorted(sub_strings, key=len, reverse=True)
    # check if the sub strings are present in reset of the strings in the list
    for sub_str in sub_strings:
        count = 0
        for string in string_list[1:]:
            if sub_str in string:
                count += 1
        if count == len(string_list[1:]):
            return sub_str
    return ''
```

Test results:
```
In [26]: longest_common_prefix(["colorado", "color", "cold"])
Out[26]: 'col'

In [27]: longest_common_prefix(["a", "b", "c"])
Out[27]: ''

In [28]: longest_common_prefix(["spot", "spotty", "spotted"])
Out[28]: 'spot'
```
