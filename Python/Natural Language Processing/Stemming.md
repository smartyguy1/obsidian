It is a text-processing task in which you reduce words to their root, which is the core part of a word. For eg: "helper" and "helping" share the root "help".
Stemming allows us to Zero-in on the basic meaning of a word.

Implementation:
```Python
from nltk.stem import PorterStemmer
from nltk.tokenize import word_tokenize
```
Now we can create stemmer
```python
stemmer = PorterStemmer()
string_for_stemming = """
... The crew of the USS Discovery discovered many discoveries.
... Discovering is what explorers do."""
```
Before we can stem the words we need to separate the words:
```python
words = word_tokenize(string_for_stemming)
```
```python
>>> words
['The',
 'crew',
 'of',
 'the',
 'USS',
 'Discovery',
 'discovered',
 'many',
 'discoveries',
 '.',
 'Discovering',
 'is',
 'what',
 'explorers',
 'do',
 '.']
```
Now to stem the words:
```python
stemmed_words = [stemmer.stem(word) for word in words]
```
now the `stemmed_words` are:
```python
>>> stemmed_words
['the',
 'crew',
 'of',
 'the',
 'uss',
 'discoveri',
 'discov',
 'mani',
 'discoveri',
 '.',
 'discov',
 'is',
 'what',
 'explor',
 'do',
 '.']
```
