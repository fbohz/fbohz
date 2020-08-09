# CSS Tricks - Centering an Image

Today we'll try to center a _Susuwatari_. These [little creatures](https://en.wikipedia.org/wiki/Susuwatari) commonly referred as 'soots' like to move around a lot so we need to keep on still and center so we can take picture of one or more of them. Let's do this!

**Note:** As you read along, please refer to the [blog's repo](https://github.com/fbohz/blogs_helper/tree/master/css/center-img).

## Adding Our Image to HTML

The need for centering an image is very common. Let's say we have our soot image and we add it with the conventional `image` tag:

```html
<img class="soot" src="soot.jpg" alt="soot!" />
```

**Don't Forget:** As you write your image tag have in mind that this tag cannot have any child nodes, that is why we don't close it. Although your browser might not complain if you have a closing `</img>`, any CSS applied to it might not work. So just follow convention above.

Now, as soon as we add our image without any CSS, the image will look like this in our page:

![Screen Shot 2020-08-09 at 4 08 17 PM](https://user-images.githubusercontent.com/15071636/89741894-a944ed80-da5a-11ea-9b4b-3c434c42ab38.png)

This is because our image is positioned accordingly to the default flow of the page, in this case on the left, same as our title.

## Centering Method 1: `margin: 0 auto`

The easiest way to center our soot will be to apply the following styling to our `img` selector:

```css
img.soot {
  margin: 0 auto;
  display: block;
}
```

Here we are adding the class name to our image selector for more specificity in case we add more soots, we need to ensure they are all centered. 

So now let's check our page any yes, our image has been centered!

![Screen Shot 2020-08-09 at 4 22 11 PM](https://user-images.githubusercontent.com/15071636/89742120-b7940900-da5c-11ea-878e-1cf9b99a4ae4.png)

So what just happened?

- Our `margin` attribute can accept four parameters, the first two top and bottom and the other left and right. Here we are basically saying for the browser to determine the left and right margins, which in this case the browser sets them equal and thus the image is centered.
- Our `display` property can have many values. In this case we choose 'block' which basically tells the img element t
- o take the whole width and on its own line. So when we apply the margin we ensure that it is applied to the whole image's width so that is why it is centered.

## Centering Method 2: `text-align: center;`

We could also center our soot by placing it inside of a parent element. Let's say a <div> and then just do text-align on the parent. To align our image make sure you add it to the parent element (often referred as container element):

```css
.container {
    text-align: center;
}
```

As our `div` element is by nature a block container, it will take the whole width and its children will be centered in this case our soot image!

## Conclusion

Pronouncing Susuwatari seems to be like a mouthful, just imagine saying it many times, at the other hand, centering images, it's actually pretty easy right!

![susuwatari-gif](https://media.giphy.com/media/hAuYWrVIyfK5G/giphy.gif)