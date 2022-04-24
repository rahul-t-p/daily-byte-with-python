> You are given a string `S` (that consists of only alphanumerical characters) and asked to reformat it into a gift card code. `S` has `N` dashes that separates the string into `N + 1` groups of characters. Every gift card code needs to contain all uppercase characters and have exactly `K` characters in each group, except the first group (but the first group must have at least one character). Given `S`, reformat it into a gift card code and return the result.
>
> Ex: Given the following values of `S` and `K`...
> - `S = "49DkeDb39LXI"`, `K = 3`, return "49D-KED-B39-LXI".
> - `S = "9Dklsi3nsEKE92"`, `K = 3` return "9D-KLS-I3N-SEK-E92".

Solution:
```
def gift_card_code(S, K):
    code = list()
    block_idxs = list(range(len(S)%K, len(S), K))

    for idx in range(len(S)):
        if idx != 0 and idx in block_idxs:
            code.append('-')
        code.append(S[idx])

    return ''.join(code).upper()
```

Test results:
```
In [4]: gift_card_code("49DkeDb39LXI", 3)
Out[4]: '49D-KED-B39-LXI'

In [5]: gift_card_code("9Dklsi3nsEKE92", 3)
Out[5]: '9D-KLS-I3N-SEK-E92'
```
