**Title Tag**: CSS Colors

**Meta Description**: Wanna make your layout stand out? Learn everything regarding applying colors with CSS. Learn CSS with CareerKarma.

**Slug**: /css-colors/

**Target Keywords**: CSS, Colors

**Author**: Felipe Bohorquez

**Twitter Message**: Wanna make your #layout stand out? Learn everything regarding applying #colors with #CSS. Learn CSS with #CareerKarma.

___

# CSS Colors Tutorial

When it comes to making your UI standout, there's nothing like choosing the right color pallette. With this tutorial you'll learn how easy it is to assign colors to elements, fonts, and pretty much anything as you build your UI.

To add color, CSS has the `**color**` data type, which represents color in the standard Red, Green, Blue (RGB) format. 


## `color` Syntax

There are 3 ways in which you can define colors with CSS:

- With **keywords**. They are typed as strings, like 'red', 'white'.
- Via `rgb()` or `rgba()` functional notations.
- Or using the HSL cylindrical-coordinate functions such as `hsl()` and `hsla()`.

## Using Keyword Identifiers

The easiest way to add a color to any element that needs it is to use keyword attributes. 

Please note that there are nuances as to the specific property you'll use to add color, being a background, a text or an element. For our example will use a good-old button.

```html
<button class="color">Color Me</button>
```

With our button element we have two options to add color. Either via the `background-color` property or the `color` property. In this case the color property changes color of the text and background-color, that of the background. Let's go ahead and select our button and then add color to our button!

Easy right?

![Screen Shot 2020-08-13 at 3 50 19 PM](https://user-images.githubusercontent.com/15071636/90185718-b88aaa80-dd7c-11ea-80ee-95177d88e325.png)

## `rgba()` and hsl() functions

So you can see how to use keywords to add color to specific color properties. You can refer to this [keyword color cheatsheet](https://www.w3.org/wiki/CSS/Properties/color/keywords) to see all the options available. Although keyword colors give us a wide array of possible colors it is limited

So you can see how these keyword colors, or pretty much any other color, with keyword or not, can be expressed also either as Hex RGB or RGB decimal. So 'black' would be #000000 or in decimal as 0,0,0 and so on. You can get more specific with these hex or decimal options. An easy way to add RGB decimal would be to use the `rgb()` function. The maximum value of each decimal is 255. Let's change our keyword colors to show these two new options:

```css
button.color {
    /* RGB and decimal */
    color: #fff;
    background-color: rgb(210,105,30);
}
```

Have you noticed that black has the same characters repeated? So when it is the same character you can just type the first three like I did for white, which can also be expressed as `#ffffff`.

Another option to add colors would be to use the `hsl()` function. HSL stands for hue, saturation, and lightness. Lightness represents a percentage from white (100%) to black (0%). Saturation is also a percentage but of the color of gray where 100% is 'full' grey color. Hue represents degrees (0 to 360) in the color wheel as RGB where 0 is red, 120 is green and 240 is blue. I know this sounds way too complicated. Code editors such as visual studio have an useful color picker you can play. Go ahead and type hsl() then hover and see the color picker pop up.

![Screen Shot 2020-08-13 at 4 18 30 PM](https://user-images.githubusercontent.com/15071636/90188660-7a43ba00-dd81-11ea-8ed6-f70281918b74.png)

The left side you can manipulate the the hue, and the two other bars saturation and lightness. Play with it and see what cool colors you can get. HSL is useful for shades, and is short is a color we can manipulate with saturation and lightness. Some people prefer it because of their own particular needs.

## Modifying Color Opacity

You might notice that both rgb and hsl functions can be expressed by either `rgba()` or `hsla()`. The 'a' stands for alpha but is pretty much the transparency / opacity where 0 is transparent and 1 is full opaque.

By modifying opacity you can get even more refined with your colors. Let's finish up our button color by modifying its opacity:

```css
button.color {
    color: #fff;
    background-color: rgba(210,105,30, 0.7);
}
```

With opacity our text reads much better indeed!

![Screen Shot 2020-08-13 at 4 36 23 PM](https://user-images.githubusercontent.com/15071636/90189665-2afe8900-dd83-11ea-8efd-d6fbe2062001.png)

