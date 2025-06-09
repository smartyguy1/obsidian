**Stop words** are words that you want to ignore, so you filter them out of your text when you're processing it.
very common words like 'in', 'is' 'an', are often used as stop words since they don't add a lot of meaning to a text.

```Python
>>> nltk.download("stopwords")
>>> nltk.download("punkt")
>>> from nltk.corpus import stopwords
>>> from nltk.tokenize import word_tokenize
```
for eg:
```python
worf_quote = "Sir, I protest. I am not a merry man!"
```
Now tokenize worf_quote by word and store the resulting list in words_in_quote:
```python
words_in_quote = word_tokenize(worf_quote)
words_in_quote
#['Sir', ',', 'I', 'protest', '.', 'I', 'am', 'not', 'a', 'merry', 'man', '!']
```
 Now to get stop words:
 ```python
 stop_words = set(stopwords.words("english"))
```
 Now we can create an empty list:
 `filtered_list = []`
 ```python
 for word in words_in_quote:
	 if word.casefold() not in stopwords:
		 filtered_list.append(word)
```
This way all the words that are not stop words are appended in the list.
```
filtered_list = ['Sir', ',', 'protest', '.', 'merry', 'man', '!']
```
Here some important words such as 'not' were also filtered out, if we want to change the stop-words we can make changes to NLTK's list of stop words in English
for example:
```python
stop_words = set(stopwords.words("english")) - {'this', 'these'}
```
or 
```python
to_remove = ['this', 'these']
new_stopwords = set(stopwords.words('english')).difference(to_remove)
```
