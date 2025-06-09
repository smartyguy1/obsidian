In a CSS selector, you can combine multiple attributes by enclosing each attribute in square brackets `[]`, without any commas or spaces between them.

### Syntax:

```css
tagname[attribute1="value1"][attribute2="value2"]
```

---

### Example:

Suppose you have an element like this:

```html
<button class="btn primary" aria-label="Dismiss sign-in info" type="button">Close</button>
```

To select this button using multiple attributes, you can do:

```python
element = driver.find_element(By.CSS_SELECTOR, 'button[class="btn primary"][aria-label="Dismiss sign-in info"]')
element.click()
```

---

### General Tips:

1. You can combine as many attributes as you need, as long as they are part of the same element.
2. You can also use partial matching like:
    - `^=` (starts with)
    - `$=` (ends with)
    - `*=` (contains)

**Example:**

```python
element = driver.find_element(By.CSS_SELECTOR, 'button[aria-label^="Dismiss"][type="button"]')
```

This selector targets a button whose `aria-label` **starts with** `"Dismiss"` and has a `type` attribute equal to `"button"`.

Let me know if you need help with more complex scenarios! 😄