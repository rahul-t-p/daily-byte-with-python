> You and a friend are trying to choose a restaurant to go to. You both give your preferences of restaurants in separate lists. You need to find a restaurant to go to that's listed in both of your preferences that has the least index sum. If there are ties, output all restaurants you could go to together.
>
> Ex: Given the following lists...
> - `list1 = ["A", "B", "C", "D"]`, `list2 = ["D", "B", "C"]`, return `["B"]` ("B" is the least index sum 1 + 1 whereas "D" is 3 + 0).
> - ``list1 = ["C"]`, `list2 = ["D"]`, return `[]`.

Solution:
```
def choose_restaurants(list1, list2):
    restaurants = []
    priority = float('inf')
    for idx in range(len(list1)):
        idx_sum = -1
        try:
            idx_sum = idx + list2.index(list1[idx])
        except ValueError:
            continue
        if idx_sum < priority:
            restaurants = [list1[idx]]
            priority = idx_sum
        elif idx_sum == priority:
            restaurants.append(list1[idx])
    return restaurants
```

Test results:
```
In [5]: choose_restaurants(["A", "B", "C", "D"], ["D", "B", "C"])
Out[5]: ['B']

In [6]: choose_restaurants(["B"], ["D"])
Out[6]: []
```