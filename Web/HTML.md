```html
<html>
These are opening and closing tags
</html>
```
The `<head><title></title><head>` gives the title to the tab we open the webpage on 
So, 
```html
<!DOCTYPE html>
<html>
    <head>
        <title>My first web page</title>
        <style>
            img {
                width: 100px;
                border-radius: 50px;
                float: left;
                margin-right: 10px;
            }
            
            .username{
                font-weight: bold;
            }
        </style>
    </head>
    <body>
        <img src="image.jpeg">
        <p class="username">@i_am_berserk001</p>
        <p>ram ram sa</p>
    </body>

</html>
```

Within the `<style> </style>` we can write CSS code. Here we want the images to have certain types of properties so we are write 
```css
img {
	width: 100px;
	border-radius: 50px;
	float: left;
	margin-right: 10px;
	}
}
```
This says that the images should have certain width, border-radius deals with the sharpness of the borders(The value of 50px makes the image round). The `float: left` attribute means the image will be at the left and the next content should begin from its right.
`margin-right` tells how much margin to leave before the next content begins.
