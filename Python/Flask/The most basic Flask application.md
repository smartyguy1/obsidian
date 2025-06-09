```python
from flask import Flask

app = Flask(__name__)

#Now we need an index route, so that we don't immediately end up on an ERROR 404
@app.route('/')
def index():
    return "Hello, World!";

if __name__ == '__main__':
    app.run(debug=True)
```

## What does this code do?
1. First we imported the `Flask` class and created an instance which is our application
2. We create an instance of this class. The first argument is the name of the application's module or package. `__name__` is a convenient shortcut for this that is appropriate for most use cases. This is needed so that Flask knows where to look for resources such as templates and static files.
3. We then use the `route()` decorator to tell Flask what URL should trigger our function.
4. The function returns the message we want to display in the user's browser. The default content type is HTML, so HTML in the string will be rendered by the browser.
## Routing

Modern web applications use meaningful URLs to help users.

Use the `route()` decorator to bind a function to a URL
```python
@app.route('/')
def index():
	return 'Index Page'

@app.route('/hello')
def hello():
	return 'Hello, World'
```
We can also make part of the URL dynamic and attach multiple rules to a function.

## Variable Rules

We can add variable sections to a URL my marking sections with `<variable_name>`. Your function then receives the `<variable_name>` as a keyword argument. Optionally, you can use a converter to specify the type of the argument like `<converter:variable_name>`.
```python
from markupsafe import escape

@app.route('/user/<username>')
def show_user_profile(username):
	# Show the user profile for that user
	return f'User {escape(username)}'

@app.route('/post/<int:post_id>')
def show_post(post_id):
	#Show the post with the given id
	return f'Post {post_id}'

@app.route('/path/<path:subpath>')
def show_subpath(subpath):
	# Show the subpath after /path/
	return f'Subpath {escape(subpath)}'
```


### Unique URLs \/ Redirection Behavior

```python
@app.route('/projects/')
def projects():
	return 'The project page'

@app.route('/about')
def about():
	return 'The about page'
```
The main URL of the `projects` is `'/'`. How this URL system works is very similar to a folder in a file system. If you access the URL without  a trailing slash (`/projects`), Flask redirects you to the canonical URL with the trailing slash `/projects/`

The canonical URL for the `about` endpoint does not have a trailing `/`. It's similar to the pathname of a file. Accessing the URL with a trailing slash (`/about/`) produces a `404 "NOT FOUND"` error. This helps keep URLs unique for these resources, which helps search engines avoid indexing the same page twice.

### URL Building

To build a URL to a specific function, use the `url_for()` function. It accepts the name of the function as it's argument and any number of keyword arguments, each corresponding to a variable part of the URL rule. Unknown variable parts are appended to the URL as query parameters.

**Why use `url_for()` for building URLs instead of hard-coding them into your templates?**

```python
from flask import url_for

@app.route('/')
def index():
	return 'index'

@app.route('/login')
def login():
	return 'login'

@app.route('/user/<username>')
def profile(username):
	return f'{username}\'s profile'

with app.test_request_context():
	print(url_for('index'))
	print(url_for('login'))
	print(url_for('login'))
	print(url_for('profile', username='John Doe'))
```
```
/ 
/login
/login?next=/
/user/John%20Doe
```

## HTTP Methods
Web applications use different HTTP methods when accessing URLs. By default, a route only answers to `GET` requests. You can use the `methods` argument of the `route()` decorator to handle different HTTP methods.

```python
from flask import requests

@app.route('/login', method=['GET', 'POST'])
def login():
	if requests.method == 'POST':
		return do_the_login()
	else:
		return show_the_login_form()
```

# Templates
Create two folders templates and static. In the templates folder create a file `index.html` with the following code:
```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="veiwport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>

<body>
    Hello World 2
</body>

</html>
```

Update the `app.py` as follows:
```python
from flask import Flask, render_template

app = Flask(__name__)

#Now we need an index route, so that we don't immediately end up on an ERROR 404
@app.route('/')
def index():
    return render_template('index.html');

if __name__ == '__main__':
    app.run(debug=True)
```

# Get support for CSS file
- Create a file `main.css` in a folder `CSS` inside the folder `static`.
```css
body {
    margin: 0;
    font-family: sans-serif
}
```
- Edit the `main.py` file to
```python
from flask import Flask, render_template, url_for

app = Flask(__name__)

#Now we need an index route, so that we don't immediately end up on an ERROR 404
@app.route('/')
def index():
    return render_template('index.html');
    
if __name__ == '__main__':
    app.run(debug=True)
```

## Render Template
To render a template you can use the `render_template()` method. All we have to do is provide the name of the template and the variable you want to pass to the template engine as keyword arguments. Here's a simple example:
```python
from flask import render_template

@app.route('/hello/')
@app.route('/hello/<name>')
def hello(name=None):
	return render_template('hello.html', person=name)
```

Flask will look for templates in the `templates` folder. So, if your application is a module, this folder is next to that module, if it's a package it's actually inside your package:

**Case 1: module**
```
/application.py
/templates
    /hello.html
```
**Case 2: Package**
```
/application
    /__init__.py
    /templates
        /hello.html
```

# Template Inheritance
Template inheritance is a very good feature of Jinja templating . Jinja is a web template engine for the Python programming language . We have seen that webpages of a website contains same footer , navigation bar etc.  So instead of making same footer and navigation bar in all webpages separately , we make use of template inheritance , which allows us to create the part which is same in all webpages (eg. footer,navigation bar) only once and we also don’t need to write the html, head, title tag again and again.

Create a file `base.html` with the following code:
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="veiwport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="{{ url_for('static', filename='css/main.css') }}">
    {% block head %}{% endblock %}
</head>
<body>
    {% block body %}{% endblock %}<!--This is for stuff like if-else statements, for loops-->
</body>
</html>
```

The `{% block %}` tags define four blocks that child templates can fill in. All the `block` tag does is tell the template engine that a child template may override those portions of the template.

Then edit `index.html` to:
```html
{% extends 'base.html' %}

{% block head %}

{% endblock %}

{% block body %}
<h1>Template</h1>
{% endblock %}
```
This(`{% <stuff> %}`) is jinja syntax.

The `{% extends %}` tag is the key here. It tells the template engine that this template “extends” another template. When the template system evaluates this template, first it locates the parent. The extends tag must be the first tag in the template.

