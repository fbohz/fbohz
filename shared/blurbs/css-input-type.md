**Title Tag**: HTML Forms: The Action Attribute

**Meta Description**: Wanna give color and style to your forms? Learn how to use CSS Input Type and take your forms to the next level! Learn CSS with CareerKarma.

**Slug**: /css-shapes/

**Target Keywords**: CSS, Forms, Input Type

**Author**: Felipe Bohorquez

**Twitter Message**: Wanna give color and style to your #forms? Learn how to use CSS Input Type and take your forms to the next level! Learn #CSS with CareerKarma.

**Word-Range**: 500 words

---

# CSS Input Type

When we are building forms we want to make them unique and appealing to our clients or customers. For it is true that the way we present them, makes their user-experience much better. In order to style our forms, we a variety of CSS input type selectors.

## Syntax and Examples

I assume that you have some experience building forms with HTML, so I will not be covering the HTML in detail. While you read this article, do refer to the accompanying **[Codepen](https://codepen.io/fbohz-the-decoder/pen/BaKZLmm)**.

Without any styling our form looks like this:

![Screen Shot 2020-08-28 at 8 21 17 PM](https://user-images.githubusercontent.com/15071636/91625329-179b1280-e96c-11ea-9cad-8848106d4656.png)

If we were in the 1990s this wouldn't be bad, I mean look at Netscape's (a popular 90s browser) [homepage](http://home.mcom.com/home/welcome.html). As we are not in the 90s, luckily today we have CSS and we can style any input just with this simple syntax:

```css
input[type="<type>"] {
  /* styles here */
}
```

**Styling Text Inputs**

The first thing we could do is style the font size of our inputs and labels. We can select them by keywords very easy as this:

```css
input,
label {
  font-size: 2rem;
  padding: 1rem;
}
```

This will make our text more legible and give some space between the inputs. With that, let's go ahead and style the text input that has the name as well as our email.

```css
input[type="text"] {
  border: 0;
  border-bottom: 0.3rem solid mediumspringgreen;
}

input[type="email"] {
  border: 0;
  border-left: 0.3rem solid mediumspringgreen;
  border-radius: 0.5rem;
}
```

The trick here is that we remove the borders and just add the specific border we need. For our email we added some radius to our border to make it look rounder. With so little style, we already made some big improvements.

![Screen Shot 2020-08-28 at 7 35 35 PM](https://user-images.githubusercontent.com/15071636/91624530-82e1e600-e966-11ea-83bb-511a09e3eaab.png)

**Caveat: Dropdowns**

Another cool styling we can apply is to our dropdowns. But there's a caveat. If we do `input[type="select"]` it would not select our dropdown. So we have to use the `select` keyword to select dropdowns.

```css 
select {
  padding: 2rem;
  font-size: 2rem;
  width: 25rem;
  border: none;
  border-bottom: 0.3rem solid mediumspringgreen;
}
```

**Other Input Stylings**

By now you should have the hang of styling inputs. Also, it seems we already have a style pattern. Let's go ahead and add our style pattern to number and date inputs.

```css
input[type="number"], input[type="date"] {
  border: 0;
  border-bottom: 0.3rem solid mediumspringgreen; 
}
```

With just a few strokes of CSS, and by using very easy selectors we are able to give another look to our inputs! 

![Screen Shot 2020-08-28 at 8 52 37 PM](https://user-images.githubusercontent.com/15071636/91625939-c8a3ac00-e970-11ea-8737-b0c3b7401bc2.png)

This is just the start. So imagine what else you can accomplish. In fact, I left some inputs unfinished at the [Codepen](https://codepen.io/fbohz-the-decoder/pen/BaKZLmm). So go ahead and apply any style you want. You already know how to do it. Go for it! 


