**Title Tag**: Creating Ranges with JavaScript

**Meta Description**: Have you ever asked yourself how to make a range with JavaScript? We'll show you different simple options to do so. Learn JavaScript with CareerKarma.

**Slug**: /javascript-range/

**Target Keywords**: JavaScript, Range, Functions, Lodash

**Author**: Felipe Bohorquez

**Twitter Message**: Have you ever asked yourself how to make a #range with JavaScript? We'll show you different simple options to do so. Learn #JavaScript with #CareerKarma.

**Word-Range**: 500 words

**STATUS**: Done

---

# Creating Ranges with JavaScript

A lot of time when writing different functions, we might want to create ranges. A range might represent data in an array or object with a beginning and end value. A lot of languages have built in methods to create ranges, for example `to_a` in Ruby:

`('a'..'e').to_a   => ["a", "b", "c", "d", "e"]`

JavaScript doesn't have a specific built-in method for this, but there are ways we can build ranges.

## `_.range()` - Lodash

If we want to create a range of numbers and we want them as fast as possible we can use the Lodash `_.range()` util method. 

This method returns and array and takes three arguments: The first for the start of the range, second for end of range (up to) and third for step, or value incremented/decremented by. If only one argument is provided it will create a range up to the number specified.

```js
_.range(-2);
// => [0, -1]
 
_.range(1, 3);
// => [1, 2]
 
_.range(1, 10, 4);
// => [1, 5, 9]

```

Remember Lodash is a JavaScript library that we need to install separately.

## Creating our own `range()` function.

If we want to save some overhead we can create our own number range function. It turns out that writing our own range is pretty easy.


```js
function range(start, end, step = 1){
  if(start === end) return [start];
  let range = [];
  for(let i = start; i <= end; i += step){
     range.push(i);
  }
  
  return range;
}

range(1, 10, 4)
//  => [1, 5, 9]
range(1, 10)
// => [ 1, 2, 3, 4,  5, 6, 7, 8, 9, 10]
```

This is easy to setup and we can avoid importing libraries such as Lodash!

## Creating a Non-number Range Function

Now you might be asking, what about non-number ranges? There are some options for us to implement that with JavaScript. Here we will use the `charCodeAt()` method to get a number that we will then increase and then push to an array using the `String.fromCharCode()` that returns a character from a character code. 

```js
function charRange(start,stop) {
  var range = [];
  let end = stop.charCodeAt(0)
  console.log(end)
  for (let i = start.charCodeAt(0); i <= end; i++){
    range.push(String.fromCharCode(i));
  }
  return range;
};

charRange('A','F')
// => [ 'A', 'B', 'C', 'D', 'E', 'F' ]

```

## Conclusion 

Now you know how easy it can be to create ranges yourself with JavaScript. Please make sure you save these handy functions, we are sure they'll be of use at some point!