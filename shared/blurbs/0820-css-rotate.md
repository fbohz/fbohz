# Rotating Elements with CSS

Today we'll learn how to rotate elements with CSS. Why should we rotate an element? We'll learn some useful applications. It will be an useful addition to your CSS toolbox.

While reading this article, please refer to the [accompanying repo](https://github.com/fbohz/blogs_helper/tree/master/css/rotate), so you can see the concepts in action.

## Rotating a Box 

Let's go ahead and create our HTML page, let's add a box as a div and give it a class (let's name it "rotate"). 

```html
    <div class="rotate"></div>
```

Now let's add some styling to it:

```css
div.rotate {
    width: 50 px;
    height: 50px;
    background-color: chocolate;
}
```

Refresh. Cool, we have a colored box:

![Screen Shot 2020-08-12 at 8 09 12 PM](https://user-images.githubusercontent.com/15071636/90083411-0699a280-dcd8-11ea-8936-5a2c035896f4.png)

In order to rotate our box, we need to discuss the `transform` property first. 

This **transform** property as the name implies, transforms elements and one of the functions we can apply to it, is `rotate()`. 

This rotate function takes one argument specifying an angle. If we pass a negative angle it will move counter-clockwise. Let's go ahead and apply a 35 degree positive rotation:

```css
div.rotate {
    width: 50 px;
    height: 50px;
    background-color: chocolate;
    transform: rotate(35deg); 
}
```

We rotated our box! Tap yourself in the back.

![Screen Shot 2020-08-12 at 8 21 25 PM](https://user-images.githubusercontent.com/15071636/90083932-7a887a80-dcd9-11ea-9677-04e5859f14bd.png)

## Useful Applications

Besides allowing for fancy UI ideas. The rotate function allows us to do a really cool animations! 

Let's go ahead and use the `:hover` selector on our div to actually apply a cool rotation effect:

```css
.rotate:hover {
    transform: rotate(35deg); 
    background-color: deeppink;
}
```

Isn't this cool? 😎

![gif-20-31-51](https://user-images.githubusercontent.com/15071636/90084463-018a2280-dcdb-11ea-8d49-183c056b74ba.gif)
