Named entities are noun phrases that refer to specific locations, people, organizations, and so on.

List of entity types from the nltk book:

| NE type      | Examples                                |
| ------------ | --------------------------------------- |
| ORGANIZATION | WHO, Georgia-pacific Corp               |
| PERSON       | Eddy Bonte, President Obama             |
| LOCATION     | Murray River, Mount Everest             |
| DATE         | June, 2008-06-29                        |
| TIME         | two fifty a m, 1:30 p.m.                |
| MONEY        | 175 million Canadian dollars, GBP 10.40 |
| PERCENT      | twenty pct, 18.75%                      |
| FACILITY     | Washington Monument, Stonehenge         |
| GPE          | South East Asia, Midlothian             |
We can use `nltk.ne_chunk()` to recognize named entities. 
eg:
```python
>>> nltk.download("maxent_ne_chunker")
>>> nltk.download("words")
>>> tree = nltk.ne_chunk(lotr_pos_tags)
```
now to look at the visual representation:
```python
>>>tree.draw()
```
output:
![[Pasted image 20240715203914.png]]
