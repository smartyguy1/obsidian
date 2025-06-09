While [[Tokenizing]] allows you to identify words and sentences, chunking allows you to identify phrases.

>A **Phrase** is a word or group of words that works as a single unit to perform a grammatical function. Noun phrases are built around a noun.
>
>Eg:
>
>- "A planet"
>- "A tilting planet"
>- "A swiftly tilting planet"

Chunking makes use of POS tags to group words and apply chunk tags to those groups. Chunks don't overlap, so one instance of a word can be in only one chunk at a time.

```python
>>> lotr_quote = "It's a dangerous business, Frodo, going out your door."
```

Now tokenize by word:
```Python
>>> words_in_lotr_quote = word_tokenize(lotr_quote)
>>> words_in_lotr_quote
['It',
 "'s",
 'a',
 'dangerous',
 'business',
 ',',
 'Frodo',
 ',',
 'going',
 'out',
 'your',
 'door',
 '.']
```
Now to tag those words by [[Tagging Parts of Speech|POS]]
```python
>>>nltk.download("averaged_perception_tagger")
>>>lotr_pos_tags = nltk.pos_tag(words_in_lotr_quote)
>>>lotr_pos_tags
[('It', 'PRP'),
 ("'s", 'VBZ'),
 ('a', 'DT'),
 ('dangerous', 'JJ'),
 ('business', 'NN'),
 (',', ','),
 ('Frodo', 'NNP'),
 (',', ','),
 ('going', 'VBG'),
 ('out', 'RP'),
 ('your', 'PRP$'),
 ('door', 'NN'),
 ('.', '.')]
```
We now have a list of tuples of all the words in the quote, along with their POS tag. In order to chunk, we first need to define a **chunk grammar**

>A **chunk grammar** is a combination of rules on how sentences should be chunked. It often uses regular expressions or**regexes**

eg:
```python
grammar = "NP: {<DT>?<JJ>*<NN>}"
```
NP stands for noun phrase.
According to the above rule, our chunks:
1. Start with an optional(?)determiner('DT')
2. Can have any number (\*) of adjectives(JJ)
3. End with a noun(\<NN>)
Create a **chunk parser** with this grammer:
```python
chunk_parser = nltk.RegexpParser(grammar)
```
Now try it with our quote:
```python
tree = chunk_parser.parse(lotr_pos_tags)
```
Now to see a visual representation of this tree:
```python
tree.draw()
```
Visual Representation
![[Pasted image 20240714211512.png|600]]
