**Title Tag**: HTML Forms: The Action Attribute

**Meta Description**: Do you really know what the HTML form tag action attribute is? Is it required on all forms? Learn HTML with CareerKarma.

**Slug**: /html-form-action/

**Target Keywords**: HTML Forms, Action Attribute.

**Author**: Felipe Bohorquez

**Twitter Message**: Do you really know what the #HTML form tag action attribute is? Is it required on all forms? Learn #HTML with CareerKarma.

**Word-Range**: 500 words

---

# CSS Font-Style

With the `font-style` CSS property we can style our font with a set of characteristics in order to give emphasis to our text. As always, checkout my [Codepen](https://codepen.io/fbohz-the-decoder/pen/xxVgKoe) so you can code-along with me.


## `font-style` Syntax and Options

We have the following options when using `font-style`. Note all of them are specified as keywords. 

```css
font-style: normal;
font-style: italic;
font-style: oblique 30deg;
font-style: oblique;
```
The normal relates to the normal font within your specified `font-family`.

With oblique we can optionally specify the angle (-90 to 90) and if no angle is specified it will default to 14. **Note that oblique and italic can be interchangeable**. This because of browser support and if you are using a special font and if the browser doesn't find or support oblique will use italic and so on. 

Before using `oblique`, do check whether the oblique keyword is [**fully supported**](https://caniuse.com/#search=oblique) on your browser.

There are also some global style keywords we can use:

```css
/* inherit from parent element */
font-style: inherit;
/* browser's default */
font-style: initial;
/* inherit if parent value, else initial */
font-style: unset;
```

Let's go ahead and add emphasis to our h1 title: 

```css
h1.title {
  font-family: 'Tangerine';
  font-style: normal;
}
```

You'll notice how we imported the Tangerine font form Google fonts, this font's normal style is cursive so it it displayed as such.

![Screen Shot 2020-08-22 at 4 42 19 PM](https://user-images.githubusercontent.com/15071636/90966304-a2749c80-e496-11ea-98f6-df06317d5d61.png)

For this particular font, making it cursive will slant it more, so probably we wouldn't wanna apply. 

## Main Use of `font-style`

In most cases using the normal keyword is redundant. Most cases you use the `font-style` property to make font italic to add emphasis. 

In order to add emphasis to a paragraph, let's make one italic.

```css
p.par {
  font-family: 'Indie Flower';
  font-style: italic;
}
```

If you checkout the [Indie Flower](https://fonts.google.com/specimen/Indie+Flower?category=Sans+Serif,Display,Handwriting&sidebar.open=true&selection.family=Indie+Flower#standard-styles) font, you'll notice it only has the regular (normal) style. In this case the browser is doing the slopping effect! 

![Screen Shot 2020-08-22 at 5 18 42 PM](https://user-images.githubusercontent.com/15071636/90966775-4876d580-e49c-11ea-96d6-b7ae7f1294f7.png)


## Conclusion

Using the `font-style` property is deeply linked with `font-family`. Until there's better browser support of the `oblique` keyword, the main use of this property would be to add emphasis on fonts by making them italic.