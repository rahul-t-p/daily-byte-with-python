> This question is asked by Amazon, Given a string representing the sequence of moves a robot vaccum makes, return whether or not it will return to its original position. The string will only contain L, R, U, and D characters, representing left, right, up and down respectively.
>
> Ex: Given the following strings...
> - "LR", return true
> - "URURD", return false
> - "RUULLDRD", return true

Solution:
```
def vacuum_cleaner_initial_position(moves):
    x_pos = moves.count('L') - moves.count('R')
    y_pos = moves.count('U') - moves.count('D')
    return True if x_pos == y_pos == 0 else False
```

Test results:
```
In [11]: vacuum_cleaner_initial_position("LR")
Out[11]: True

In [12]: vacuum_cleaner_initial_position("URURD")
Out[12]: False

In [13]: vacuum_cleaner_initial_position("RUULLDRD")
Out[13]: True
```