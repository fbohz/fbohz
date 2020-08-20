**Title Tag**: ID and Class in HTML and Their CSS Selectors

**Meta Description**: Master HTML IDs and class attributes and the most important CSS Selectors

**Slug**: /html-css-class-id/

**Target Keywords**: HTML, CSS, IDs, Classes, Selectors.

**Author**: Felipe Bohorquez

**Twitter Message:** Do you know how to uniquely identify an #HTML element? How about a group of elements? Can you apply style to one or more elements? Learn #HTML and #CSS class and ID selectors with #CareerKarma.

___

# ID and Class Attributes in HTML and Their CSS Selectors

When using CSS for styling web pages, you'll often want to target certain parts of your page. One of the ways you can select element is by either their ID and/or Class attributes.

As you through this tutorial, checkout the interactive [Codepen](https://codepen.io/fbohz-the-decoder/pen/ZEWpMJL) and play along with me!

## The ID Attribute

Let's go ahead and make a simple paragraph, using the `<p>` tag:

```html
    <p> Color this paragraph! </p>
```

An ID is an **unique** identifier you add to your elements to uniquely identify them. It follows the convention `id="#NAME"`. With that in mind, and since we want to color our paragraph, let's name our it with an unique name. 

```html
    <p id="paragraph-colored"> Color this paragraph! </p>
```

Now that we have our ID unique identifier, we need to ensure we don't add it to another element. While the browser will not complain, it will loose the purpose and the CSS will not work as intended. 

With our ID in place, we can selecting using the hashtag symbol `#` with CSS. Let's make our p tag blue:

```css
#paragraph-colored {
  color: blue;
}
```

Easy-peasy right? 😄

## The Class Attribute

Cool we have our paragraph with the text colored blue. Let us now suppose we have a bunch of avocados images beneath our single p tag:

```html
<img src="https://avatars1.githubusercontent.com/u/43709642?s=280&v=4" alt="avocado">
<img src="https://avatars1.githubusercontent.com/u/43709642?s=280&v=4" alt="avocado">
<img src="https://avatars1.githubusercontent.com/u/43709642?s=280&v=4" alt="avocado">
```

![Screen Shot 2020-08-19 at 8 38 48 PM](https://user-images.githubusercontent.com/15071636/90706960-0a8b6e80-e25c-11ea-8fa1-8ed4a4b512df.png)

How could we identify and select all these avocado-developers (whatever that means)? We know we cannot use the ID tag, because that is used to uniquely identify a single item. This is where the class attribute comes to play.

The class attribute follows the convention `class="#CLASS_NAME"`. Since many members can belong to a class, all our avocado developers could be assigned a class such as:

```html
<img src="https://avatars1.githubusercontent.com/u/43709642?s=280&v=4" alt="avocado" class="avocado-devs">
```

Great our avocado images have been assigned the class "avocado-devs". We can now use the CSS class selector that is represented by a simple dot (`.`). Let's go ahead and add the CSS filter property to our avocado devs. We'll suppose they are working late at night so let's invert their colors.

```css
.avocado-devs {
  filter: invert(100)
}
```

With classes we basically create groups and then with the CSS class selector we can apply styles as we want.

## Using Generic Tag Selectors with Class Selectors

We often see that when selecting classes with CSS it is better to use generic tag selectors in conjunction with the dot selector. Why? Because the more specific we are with our selectors, our CSS will apply much better. 

With CSS, we use generic tag selectors by pretty much referring them by the tag name. So for example these are all valid tag selectors:

```css
/* H1 */ 
h1{}
/* Paragraphs */ 
p{ }
```

So we could refactor our image selector by using the `img` generic tag:

```css
img.avocado-devs {
  filter: invert(100)
}
```

The functionality hasn't changed, but as your code grows this specificity is important. It will make your code also more readable. Other developers will see that the avocado-devs class refers to an image.  

This is important because here we only apply the filter to images that have the specific class name. If we were to add another avocado-dev image without the appropriate class the style will not apply. As web developers this conditional behavior, is what we often want.