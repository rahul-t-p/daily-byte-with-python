> This question is asked by Amazon. Given two strings representing sentences, return the words that are not common to both strings (i.e. the words that only appear in one of the sentences). You may assume that each sentence is a sequence of words (without punctuation) correctly separated using space characters.
>
> Ex: given the following strings...
> - sentence1 = "the quick", sentence2 = "brown fox", return ["the", "quick", "brown", "fox"]
> - sentence1 = "the tortoise beat the haire", sentence2 = "the tortoise lost to the haire", return ["beat", "to", "lost"]
> - sentence1 = "copper coffee pot", sentence2 = "hot coffee pot", return ["copper", "hot"]

Solution:
```
def uncommon_words(sentence1, sentence2):
    words1, words2 = set(sentence1.split()), set(sentence2.split())
    return list(words1^words2)
```

Test results:
```
In [22]: uncommon_words("the quick", "brown fox")
Out[22]: ['quick', 'the', 'fox', 'brown']

In [23]: uncommon_words("the tortoise beat the haire", "the tortoise lost to the haire")
Out[23]: ['beat', 'to', 'lost']

In [24]: uncommon_words("copper coffee pot", "hot coffee pot")
Out[24]: ['copper', 'hot']
```
