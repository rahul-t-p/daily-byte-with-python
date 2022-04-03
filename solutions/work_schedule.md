> You are given an array of interval objects, which each consist of a `start` time and an `end` time. Each interval object represents when a particular meeting starts and ends. Return whether or not someone could attend every meeting.
>
> Ex: Given the following intervals...
> - `intervals = [[1, 3], [5, 10]]`, return true.
> - `intervals = [[1, 8], [5, 9]]`, return false.

Solution:
```
def can_attend_all_meetings(intervals):
    sorted_intervals = sorted(intervals)
    end_interval = 0
    for meeting in sorted_intervals:
        if end_interval > meeting[0]:
            return False
        end_interval = meeting[1]
    return True
```

Test results:
```
In [2]: intervals = [[1, 3], [5, 10]]

In [3]: can_attend_all_meetings(intervals)
Out[3]: True

In [4]: intervals = [[1, 8], [5, 9]]

In [5]: can_attend_all_meetings(intervals)
Out[5]: False

```
