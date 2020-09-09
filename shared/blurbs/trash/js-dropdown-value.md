**Title Tag**: How to Get Dropdown Values with JavaScript

**Meta Description**: Learn how to use JavaScript to get dropdown values on HTML forms. Learn JavaScript with CareerKarma.

**Slug**: /js-dropdown-value/

**Target Keywords**: JavaScript, HTML Forms, Dropdown, Value

**Author**: Felipe Bohorquez

**Twitter Message**: Learn how to use #JavaScript to get dropdown values on #HTML forms. Learn JavaScript with #CareerKarma.

**Word-Range**: 500 words

**STATUS**: Done

---

# How to Get Dropdown Values with JavaScript

As you learn how to build web forms, one of the most common tasks is to get values from the dropdown element. In this article we'll learn how to get such values with JavaScript.

## Dropdown HTML Element

Let's have a quick recap as to how to build a dropdown element using HTML. Do follow my [Codepen](https://codepen.io/fbohz-the-decoder/pen/poydyXB) if you get lost.

Now in order to build our dropdown element we need to use the `select` tag and use `option` children nested under it. The select element creates the dropdown and with the option tags we define those options inside the dropdown.

Let's create a dropdown of our favorite fruits (that have emojis).

```html
<select name="fruits" id="fruits">
  <option value="">--select--</option>
  <option value="avocado">Avocado🥑</option>
  <option value="watermelon">Watermelon🍉</option>
  <option value="kiwi">Kiwi🥝</option>
  <option value="tomato">Tomato🍅</option>
</select>

<h2 id="pick"></h2>
```

We added an empty h2 that we will populate with JavaScript later. So now you can pick your favorite fruit:

![Screen Shot 2020-09-03 at 1 14 49 PM](https://user-images.githubusercontent.com/15071636/92151925-81da0a00-ede7-11ea-9796-2a8a506c4a6e.png)

Notice how the importance of adding **values**. The values property gives us non-stylized information we can easily play with JavaScript. At the other hand the text inside the option tag can be pretty much anything. The value property is what is important here.

## Selecting and Displaying Dropdown Value with JavaScript

First of all we need to select our fruits dropdown by using `getElementById` on the select tag.

```js
const element = document.getElementById("fruits");
```

Now that our dropdown is selected we can get the value of the currently selected option. This by default is the first option. Let's try that:

```js
const checkValue = element.options[element.selectedIndex].value;
const checkText = element.options[element.selectedIndex].text;
```

Here we are accessing the elements options array attribute. Then we select the index of the currently selected option and access its value or text. Now try to console.log both variables. What happens? Nothing. Why? Because our first element has an empty value (it's just a placeholder). Comment out the first option and try again. Yay! We get both the value and text with javascript.

## Listening for Dropdown Changes with JavaScript

We should make our selection dynamic since JavaScript is designed to react for changes in your page. With that in mind we will assign an `eventListener` to our fruit element.

```js
element.addEventListener("change", (e) => {
  const value = e.target.value;
  const text = element.options[element.selectedIndex].text;

  if (value) {
    document.getElementById("pick").textContent = `Value Selected: ${value}`;
  } else {
    document.getElementById("pick").textContent = "";
  }
});
```

With our eventListener we are listening for a change in our dropdown. Then here I show you that you can also get the value of the selected option by doing `e.target.value` which you've probably seen in another forms.

So now you can try to select and JavaScript is reacting to changes in our dropdown and updating our h2 accordingly!

![Sep-03-2020 13-50-43](https://user-images.githubusercontent.com/15071636/92155152-88b74b80-edec-11ea-8016-7f8911f26735.gif)

## Conclusion

Getting dropdown values is a crucial skill as you learn web development. The values we get are important if we want to update a database, just show the selection to the user or just 'react' to DOM changes. With JavaScript we can get such values in no time.
