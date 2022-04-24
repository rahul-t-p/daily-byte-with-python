> You are playing a game with a friend. In this game you’re given a string `s` and you and your friend take turns making moves. A move consists of flipping two consecutive `+` signs into `-` signs. Given a string `s`, return a list containing all possible states of s after you've made the first move.
>
> Ex: Given the following string `s`...
> - `s = "++"`, return ["--"].
> - `s = "++++", return ["--++","+--+","++--"].

Solution:
```
def plus_to_minus(s):
    possible_next_states = list()
    for idx in range(len(s)):
        if s[idx] == '+' and idx < len(s)-1:
            if s[idx+1] == '+':
                possible_next_states.append(s[:idx]+'--'+s[idx+2:])
    return possible_next_states
```

Test results:
```
In [9]: plus_to_minus("++")
Out[9]: ['--']

In [10]: plus_to_minus("++++")
Out[10]: ['--++', '+--+', '++--']
```
