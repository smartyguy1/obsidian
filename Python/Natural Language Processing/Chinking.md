It is used together with [[Chunking]], but while chunking is used to include a pattern, chinking is used to exclude a pattern.

Let's reuse the quote you used in the section on chunking:
```python
>>> lotr_pos_tags
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
Now to create a grammar to determine what to include and exclude in your chunks.
We are using more than one line because we are going to have more than one rule.
```python
>>>grammar = """
	Chunk : {<.*>+}
			}<JJ>{"""
```
The first rule of our grammar is `{<.*>+}`. This rule has inward curly braces to denote the pattern we want to include. In this case we want to include everything: `{<.*>+}`

The 2nd rule is `}<JJ>{`. This rule has outward curly braces because it denotes the patterns we want to exclude. In this case, we want to exclude adjectives: \<JJ>

Create a chunk parser with this grammar:
```python
chunk_parser = nltk.RegexpParser(grammar)
```
Now chunk our sentence with the chink we specified:
```python
>>>tree = chunk_parser.parse(lotr_pos_tags)
```
Result:
```python
tree.draw()
```
![[Pasted image 20240714213012.png|600]]
