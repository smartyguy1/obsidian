**Part of speech** is a grammatical term that deals with the roles words play when we use then together in sentences. Tagging parts of speech, or **POS tagging**, is the task of labeling the words in your text according to their part of speech.

In English, there are eight parts of speech:

| Parts of speech | Role                                                                | Ex:                        |
| --------------- | ------------------------------------------------------------------- | -------------------------- |
| Noun            | Is a person, place or thing                                         | mountain, bagel, Poland    |
| Pronoun         | Replaces a noun                                                     | you, she, we               |
| Adjective       | Gives info about what noun is like                                  | efficient, windy, colorful |
| Verb            | is an action or a state of being                                    | learn, is, go              |
| Adverb          | Gives info about a verb, an adjective, or another adverb            | efficiently, always, very  |
| Preposition     | Gives info about how a noun or pronoun is connected to another word | from, about, at            |
| Conjunction     | Connects two other words or phrases                                 | so, because, and           |
| Interjection    | Is an excalmation                                                   | yay, ow, wow               |
| articles        |                                                                     | a, the                     |
NLTK uses the words determiner to refer to articles.

```python
>>> sagan_quote = """
... If you wish to make an apple pie from scratch,
... you must first invent the universe."""
```
First tokenize to separate the words:
```Python
words_in_sagan_quote = word_tokenize(sagan_quote)
```

==Call `nltk.pos_tag()`==
```python
>>> import nltk
>>> nltk.pos_tag(words_in_sagan_quote)
[('If', 'IN'),
 ('you', 'PRP'),
 ('wish', 'VBP'),
 ('to', 'TO'),
 ('make', 'VB'),
 ('an', 'DT'),
 ('apple', 'NN'),
 ('pie', 'NN'),
 ('from', 'IN'),
 ('scratch', 'NN'),
 (',', ','),
 ('you', 'PRP'),
 ('must', 'MD'),
 ('first', 'VB'),
 ('invent', 'VB'),
 ('the', 'DT'),
 ('universe', 'NN'),
 ('.', '.')]
```
All the words in the quote are now in a separate tuple, with a tag that represents their part of speech.

To get a list of tags and their meanings:
```python
nltk.help.upenn_tagset()
```

Summary of tags:

| Tags that start with | Deal with  |
| -------------------- | ---------- |
| JJ                   | Adjectives |
| NN                   | Nouns      |
| RB                   | Adverbs    |
| PRP                  | Pronouns   |
| VB                   | Verbs      |
