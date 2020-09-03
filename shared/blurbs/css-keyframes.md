**Title Tag**: CSS Keyframes

**Meta Description**: Do you know how to make animations using CSS? Learn how to define your own animations using keyframes! Learn CSS with CareerKarma.

**Slug**: /css-keyframes/

**Target Keywords**: CSS, Animations, Keyframes

**Author**: Felipe Bohorquez

**Twitter Message**: Do you know how to make animations using #CSS? Learn how to define your own animations using #keyframes! Learn CSS with #CareerKarma.

**Word-Range**: 500 words

**STATUS**: DONE

---

# CSS Keyframes

Building animations is a breeze with CSS. And the fun part is that you don't need any third party frameworks or plugins. `@keyframes` CSS rule is a tool we need under our belt to build these animations.

## `@keyframes` Syntax

The @keyframes is a CSS at-rule. At-rules tells how CSS should behave. There are many other at-rules such as @viewport, @supports and many more.

We define a @keyframes rule with the following syntax.

```css
@keyframes <name> {
  from {
    /* start details here */
  }

  to {
    /* end details here */
  }
}
```

We can get more refined animation declarations by specifying percentages instead of keywords.

```css
@keyframes <name> {
  0% {
  }
  50% {
  }
  100% {
  }
}
```

In order to use our newly created keyframe we need to add it as a value of the `animation-name` property. We should also set the `animation-duration` to specify the duration of our declared @keyframes animation.

## Magic Ball Example

Let's go ahead and make a magic ball appear and disappear. Do refer to the accompanying [Codepen](https://codepen.io/fbohz-the-decoder/pen/OJNxrvX) if you get lost at any point.

The first thing we need to do is define our animation. We'll name it magic-ball:

```css
@keyframes magic-ball {
  from {
    background-color: limegreen;
  }
  to {
    background-color: blueviolet;
  }
}
```

Here basically we are changing the background color from limegreen to blueviolet. This can be applied to any element, but we'll go ahead and apply it to a circle.

```css
.circle {
  width: 10rem;
  height: 10rem;
  border-radius: 50%;
  animation-name: magic-ball;
  animation-duration: 4s;
}
```

Do not forget that in order for our keyframe animation to work with need to add it as a value of the `animation-name` property and set an animation duration in seconds by using `animation-duration`. So now our ball is appearing and disappearing!💥

![Sep-02-2020 22-48-04-ball](https://user-images.githubusercontent.com/15071636/92069334-ae057480-ed6e-11ea-9e22-9bffdf1c7b1b.gif)

## Flash Sale Example

Let's go ahead and create our animation. This time let's animate a square and create a moving effect. We'll name our animation moveIn and in this case we'll use percentages.

```css
@keyframes moveIn {
  0% {
    opacity: 0;
    transform: translateY(3rem);
  }
  100% {
    opacity: 1;
    transform: translate(0);
  }
}
```

Opacity is pretty much our transparency. We can apply this newly created animation to our square and with very little we have accomplished a fine effect!

![Sep-02-2020 22-49-54-square](https://user-images.githubusercontent.com/15071636/92069332-ac3bb100-ed6e-11ea-8588-7f7d5f6e5000.gif)


```css
.square {
  width: 10rem;
  height: 10rem;
  background-color: greenyellow;
  animation-name: moveIn;
  animation-duration: 4s;
  font-size: 3rem;
  color: whitesmoke;
  text-align: center;
}
```

## Conclusion

You can continue your journey on animations by reading the [CSS documentation on animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations). Also note, we only referred to one way to refine our animations by using its duration. There are many more [animation sub-properties](https://www.freecodecamp.org/news/how-to-use-animations-in-css/) worth looking!

Finally, do have in mind that not all properties can be animated. Look at this exhaustive list of [animated properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties).
