> Given a paragraph and a list of banned words, return the most frequently occurring word that is not banned. Treat words case insensitively and ignore punctuation.
>
> Ex: Given the following `paragraph` and list of `banned` words...
> - `paragraph = "The daily, the byte Daily."`, `banned = ["the"]`, return "daily".

Solution:
```
# Note: If multiple items are most frequent, the function returns the first one encountered
def most_frequent_word(paragraph, banned):
    frequent_word = ''
    sentence_list = ''.join(filter(lambda c: c.isalpha() or c == ' ', paragraph.lower())).split()
    for word in sentence_list.copy():
        if word in banned:
            sentence_list.remove(word)
    if sentence_list != []:
        frequent_word = max(set(sentence_list), key=sentence_list.count)
    return frequent_word
```

Test results:
```
In [4]: paragraph = "The daily, the byte Daily." ; banned = ["the"]

In [5]: most_frequent_word(paragraph, banned)
Out[5]: 'daily'
```
