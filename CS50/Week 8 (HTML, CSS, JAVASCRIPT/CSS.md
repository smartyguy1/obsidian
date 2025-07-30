*cascading style sheet*, is a markup language that allows you to fine-tune the aesthetics of your HTML files.

CSS is filled with properties, which include key-value pairs.

```html
<!DOCTYPE html>

<!-- Demonstrates inline CSS with P tags -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body>
        <p style="font-size: large; text-align: center;">
            John Harvard
        </p>
        <p style="font-size: medium; text-align: center;">
            Welcome to my home page!
        </p>
        <p style="font-size: small; text-align: center;">
            Copyright &#169; John Harvard
        </p>
    </body>
</html>
```
Notice that some style attributes are provided to the `<p>` tags. The `font-size` is set to `large`, `medium` and `small`. Then `text-align` is set to center.

We can improve the above code as:
```html
<!DOCTYPE html>

<!-- Removes outer DIV -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body style="text-align: center">
        <div style="font-size: large">
            John Harvard
        </div>
        <div style="font-size: medium">
            Welcome to my home page!
        </div>
        <div style="font-size: small">
            Copyright &#169; John Harvard
        </div>
    </body>
</html>
```
Notice that `<div>` tags are used to divide up this HTML file into specific regions. `text-align: centre` is invoked on the entire body of the HTML. Because everything inside `body` is a child of `body`, the `center` attribute cascades down to those children.

It turns out there are newer semantic tags included in HTML. We can modify our code as :
```html
<!DOCTYPE html>

<!-- Uses semantic tags instead of DIVs -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body style="text-align: center">
        <header style="font-size: large">
            John Harvard
        </header>
        <main style="font-size: medium">
            Welcome to my home page!
        </main>
        <footer style="font-size: small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```
Notice that the `header` and `footer` both have different styles assigned to them.

This practice of placing the style and information all in the same location is not good practice. We could move the elements of style to the top of the file as follows:

```html
<!-- Demonstrates class selectors -->

<html lang="en">
    <head>
        <style>

            .centered
            {
                text-align: center;
            }

            .large
            {
                font-size: large;
            }

            .medium
            {
                font-size: medium;
            }

            .small
            {
                font-size: small;
            }

        </style>
        <title>css</title>
    </head>
    <body class="centered">
        <header class="large">
            John Harvard
        </header>
        <main class="medium">
            Welcome to my home page!
        </main>
        <footer class="small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```
Notice that all the style tags are places up in the `head` in the `style` tag wrapper. Also, notice that we've assigned *classes*, called `centered`, `large`, `medium` and `small` to our elements, and that we select those classes by placing a dot before the name, as in `.centered`.

It turns out we can move all out style code into a special file called a CSS file. We can create a file called `style.css` and paste our classes there.
```css
.centered
{
    text-align: center;
}

.large
{
    font-size: large;
}

.medium
{
    font-size: medium;
}

.small
{
    font-size: small;
}
```
Notice that this is verbatim what appeared in our HTML file.

We can tell the browser where to locate the CSS for this HTML file:
```html
<!DOCTYPE html>

<!-- Demonstrates external stylesheets -->

<html lang="en">
    <head>
        <link href="style.css" rel="stylesheet">
        <title>css</title>
    </head>
    <body class="centered">
        <header class="large">
            John Harvard
        </header>
        <main class="medium">
            Welcome to my home page!
        </main>
        <footer class="small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```