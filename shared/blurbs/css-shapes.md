**Title Tag**: HTML Forms: The Action Attribute

**Meta Description**: Do you really know what the HTML form tag action attribute is? Is it required on all forms? Learn HTML with CareerKarma.

**Slug**: /css-shapes/

**Target Keywords**: HTML Forms, Action Attribute.

**Author**: Felipe Bohorquez

**Twitter Message**: Do you really know what the #HTML form tag action attribute is? Is it required on all forms? Learn #HTML with CareerKarma.

**Word-Range**: 500 words

**STATUS**: DONE

---

# CSS Shapes

Let's go ahead and create some fun CSS shapes! Follow my [Codepen](https://codepen.io/fbohz-the-decoder/pen/abNWbWQ) for all the code. Let's do this.

## Rectangles and Squares

All our shapes will be wrapped in a `div`. The most basic shape is the square and the rectangle since by default the div is a square or rectangle depending on the `width` and `height` properties. So the square has equal width and height whereas rectangle doesn't:

```css
.rectangle {
  width: 2rem;
  height: 4rem;
  background-color: violet;
}

.square {
  width: 5rem;
  height: 5rem;
  background-color: lime;
}
```

**Reminder**: REMs are based on the root font-size and allow to easy scale. This is default on the browser (usually 16px). We set our font-size to 20px, so 2rem is 40px.

Pretty easy right?

![Screen Shot 2020-08-26 at 1 13 11 PM](https://user-images.githubusercontent.com/15071636/91341855-c8a08200-e79f-11ea-9b6b-4a16edc30f5a.png)

## Circle

We'll go ahead and create a circle for a profile image. To create a circle is similar to the square but we need to specify the `border-radius`. To round the corners, will have to be at 50%. If we want an oval we'll modify the width/height similar vein as rectangle.

Let's make our profile image:

```css
.profile-image {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-image: url("https://user-images.githubusercontent.com/15071636/91342237-57ad9a00-e7a0-11ea-97bc-606a5998b29a.jpg");
  background-position: center center;
  background-size: cover;
}
```

The `background` properties are to get the image, size it, and center it.

![Screen Shot 2020-08-26 at 1 37 46 PM](https://user-images.githubusercontent.com/15071636/91344330-6ba6cb00-e7a3-11ea-91f6-44cc8103c082.png)

## Parallelogram

We can also make a parallelogram. This shape can be useful when adding a cool text effect. Here we'll use the `transform` property and we'll use the `skew` property value to transform the shape (and anything inside) as a parallelogram with either 20 or -20 degrees.

```css
.parallelogram {
  color: ivory;
  width: 6rem;
  height: 1.5rem;
  transform: skew(-20deg);
  background: indianred;
}
```

![Screen Shot 2020-08-26 at 2 36 03 PM](https://user-images.githubusercontent.com/15071636/91348522-811ef380-e7a9-11ea-8d2b-0cfee030db08.png)

Looks cool right 😎.

## Other Shapes

Now that we have some knowledge of CSS shapes and its uses, we can take a look at other shapes. All of them you can check out play for yourself on [Codepen](https://codepen.io/fbohz-the-decoder/pen/abNWbWQ).

![Screen Shot 2020-08-26 at 2 46 07 PM](https://user-images.githubusercontent.com/15071636/91349625-300fff00-e7ab-11ea-8717-9f7fa50685ae.png)

```css
.triangle {
  width: 0;
  height: 0;
  border-left: 2rem solid transparent;
  border-right: 2rem solid transparent;
  border-bottom: 5rem solid hotpink;
}
```

While there are many ways to do a heart, and you can find many iterations of it online, this one is pretty straightforward.

![Screen Shot 2020-08-26 at 3 14 18 PM](https://user-images.githubusercontent.com/15071636/91352075-ea553580-e7ae-11ea-8e46-4a93cec0008b.png)

```css
.heart {
  width: 10rem;
  background: radial-gradient(circle at 60% 65%, goldenrod 64%, transparent 65%)
      top left, radial-gradient(
        circle at 40% 65%,
        goldenrod 64%,
        transparent 65%
      ) top right,
    linear-gradient(to bottom left, goldenrod 43%, transparent 43%) bottom left,
    linear-gradient(to bottom right, goldenrod 43%, transparent 43%) bottom right;
  background-size: 50% 50%;
  background-repeat: no-repeat;
}

.heart::before {
  content: "";
  display: block;
  padding-top: 100%;
}
```

Go ahead and play with the percentages and change the colors. You can see how the heart is being built. So we can see how with the `::before` and also `::after` pseudo-elements, we can make some cool shapes.

Also, with the `polygon()` function we can specify other shapes, expanding our limits.

![Screen Shot 2020-08-26 at 3 26 05 PM](https://user-images.githubusercontent.com/15071636/91353240-9d725e80-e7b0-11ea-997e-8e4fb53bbf90.png)

```css
.letter-t {
  width: 5rem;
  height: 5rem;
  margin: 0 1rem;
  shape-outside: polygon(
    0 0,
    100% 0,
    100% 20%,
    60% 20%,
    60% 100%,
    40% 100%,
    40% 20%,
    0 20%
  );
  clip-path: polygon(
    0 0,
    100% 0,
    100% 20%,
    60% 20%,
    60% 100%,
    40% 80%,
    40% 20%,
    10% 20%
  );
  background: navajowhite;
}
```

Checkout this [clip-path maker](https://bennettfeely.com/clippy/), a cool tool that will generate for you the code for a bunch of shapes.
