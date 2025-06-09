Like [[Stemming]], lemmatizing reduces words to their core meaning, but it will give you a complete English word that makes sense on its own instead of just a fragment of a word like `'discoveri'`

>A **lemma** is a word that represents a whole group of words, and that group of words is called a **lexeme**.
>
>For eg: "Blend" is the **lemma** and 'Blending' is part of the **lexeme**

Import relevant parts:
```python
from nltk.stem import WordNetLemmatizer
```
Create a lemmatizer to use:
```python
lemmatizer = WordNetLemmatizer()
```
Eg:
```python
>>> lemmatizer.lemmatize("scarves")
'scarf'
```
```python
>>> lemmatizer.lemmatize("worst")
'worst'
```
Here, `lemmatizer.lemmatize()` assumed that "worst" was a noun. We can make it clear that "worse" is an adjective:
```python
>>> lemmatizer.lemmatize("worst", pos="a")
'bad'
```
The default parameter for pos is 'n' for noun, but we made sure "worst" was treated as an adjective by adding parameter, `pos = "a"`.
"worst" is the superlative form of the adjective 'bad', and lemmatizing reduces
superlatives as well as comparatives to their lemmas.

**This is why it is important to [[Tagging Parts of Speech|tag words]] before lemmatizing them.**
