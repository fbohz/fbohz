**Title Tag**: HTML Forms: The Action Attribute

**Meta Description**: Do you really know what the HTML form tag action attribute is? Is it required on all forms? Learn HTML with CareerKarma.

**Slug**: /css-z-index/

**Target Keywords**: HTML Forms, Action Attribute.

**Author**: Felipe Bohorquez

**Twitter Message**: Do you really know what the #HTML form tag action attribute is? Is it required on all forms? Learn #HTML with CareerKarma.

**Word-Range**: 500 words

---

# CSS Z-Index

When you are designing your layout with CSS, often you'll be positioning elements either up/down or left/right. The `z-index` allows us to move elements on a 3rd dimension on the Z-axis, with a stacking effect.

The `z-index` property takes either the `auto` keyword or an integer. These are all valid declarations:

```css
z-index: auto;
z-index: -1;
z-index: 9999;
```

**Note**: In order for the z-index to apply, we need to position elements, using the `position` property either as relative, absolute or fixed. If no position is specified it will be the same as applying `z-index: auto` as no stacking context will be applied by z-index.

Let's take a look at an example.

## Let's position some Guiniea Pigs

You can check this example at my [Codepen](https://codepen.io/fbohz-the-decoder/pen/XWdpeWg). Play around with it and code with me!

We'll be placing two Guinea pigs, or *Cuys* (which sounds way cuter). Let's imagine we are in summer so it's 90+ degrees outside. Our Cuy#1 will be placed inside a lake, she'll have a good time. Cuy#2 is very lazy so we need to give him some coffee to wake him up! So we'll stack our Cuy#2 with the coffee so he can drink it.

Without any positioning or CSS our images look more or less like this:

![Screen Shot 2020-08-23 at 6 47 02 PM](https://user-images.githubusercontent.com/15071636/90991873-e6889f80-e571-11ea-91dd-753c9b8e4e62.png)

The idea is to create a stacking context using z-index to then position some images on top of each of the lake and the coffee. Also, remember we need to add positioning to our elements in order for z-index to apply. Let's go ahead and position our Cuy#1:

```css
img.cuy.one {
  position: absolute;
}
```

Where the hell is our friend? Let's go ahead and add a higher stacking context so it is on top of the lake:

```css
img.cuy.one {
  position: absolute;
  z-index: 1;
}
```

Yay! Our cuy is on top of the lake. We now need to add some padding to place it inside the lake, but I'll leave you to play with that.

Now that we know how to create a stacking context using `z-index` and positioning, we can place our second cuy very easy:

```css
img.cuy.two {
  position: absolute;
  width: 160px;
  padding: 100px;
  z-index: 1;
}
```

Again padding will be for exact positioning of the image, width is used to only specify the size of our little friend. With this, we have finished our task and everyone is happy and feels refreshed:

![Screen Shot 2020-08-23 at 7 21 58 PM](https://user-images.githubusercontent.com/15071636/90992553-379a9280-e576-11ea-8e44-e7a7e36740d7.png)

## Conclusion

Playing around with `z-index` makes way for interesting layout ideas. On the [Codepen](https://codepen.io/fbohz-the-decoder/pen/XWdpeWg) I have provided a second example of a pop chat design positioned and with z-index on top of everything.

Do not forget that you must always position elements or your z-index will not work, try to play around the Codepen by removing the positioning and see it for yourself. Another recommendation if that you must apply z-index to sibling elements. In our examples our images were not nested and were siblings (side-by-side). If you have deeply nested elements z-index might not work as expected, so have that in mind.