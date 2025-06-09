# Tokenizing 
- Split text word-by-word or sentence-by-sentence. 
- This allows us to work with smaller pieces of text that are still relatively coherent and meaningful even outside the context of the text.
1. **Tokeninzing by word**:
	This allows us to identify words that come up particularly often.
	eg: *finding how many times word Python appears in Job applications*
2. **Tokenizing by sentence**:
	We can analyze how the words relate to each other and see more context.
	eg: *Are there a lot of negative words around the word "Python"?*


To import relevant parts of NLTK:
```python
from nltk.tokenize import sent_tokenize, word_tokenize
```

```python
>>> example_string = """
... Muad'Dib learned rapidly because his first training was in how to learn.
... And the first lesson of all was the basic trust that he could learn.
... It's shocking to find how many people do not believe they can learn,
... and how many more believe learning to be difficult."""
```

We can use sent_tokenize() to split up `example_string` into sentences:
```python
>>> sent_tokenize(example_string)
["Muad'Dib learned rapidly because his first training was in how to learn.",
'And the first lesson of all was the basic trust that he could learn.',
"It's shocking to find how many people do not believe they can learn, and how many more believe learning to be difficult."]
```
This give us a list of strings that are sentences

To tokenize by word:
```python
>>> word_tokenize(example_string)
["Muad'Dib",
 'learned',
 'rapidly',
 'because',
 'his',
 'first',
 'training',
 'was',
 'in',
 'how',
 'to',
 'learn',
 '.',
 'And',
 'the',
 'first',
 'lesson',
 'of',
 'all',
 'was',
 'the',
 'basic',
 'trust',
 'that',
 'he',
 'could',
 'learn',
 '.',
 'It',
 "'s",
 'shocking',
 'to',
 'find',
 'how',
 'many',
 'people',
 'do',
 'not',
 'believe',
 'they',
 'can',
 'learn',
 ',',
 'and',
 'how',
 'many',
 'more',
 'believe',
 'learning',
 'to',
 'be',
 'difficult',
 '.']
```
Now we got a list of strings that NLTK considers to be words such as:
- "Muad'Dib"
- "training"
But these strings were also considered to be words:
- "`'s`"
- "`,`"
- "`.`"
*"It's" was split to give "It" and " 's " because NLTK knows that 'It'  and " 's "are two distinct words*
