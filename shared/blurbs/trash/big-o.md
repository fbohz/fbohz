---
layout: post
title: "Simply Big-O"
# date:       2020-06-15 19:31:03 -0400
permalink: big-o
filename: 2020-07-15-big-o
---

> If you apply 100 companies, it can be that 1% would actually get back to you. Starting this week I'll begin some exploration on computer science concepts so you too can increase your response percentage to 5% or more.

# Simply BIG-O

**What is good code?**

It usually means Readable and Scalable. _BIG O means scalable code_:

- Scalable means speed. It also means memory.
- What's the memory usage of code? You can use Big O for this too.
- Memory vs. Speed is usually a sacrifice. You get better speed you might have more memory.

Note 'faster code' (in terms how long it takes to compile) also depends of what CPU you have, the server etc. So it's hard to measure good code, in terms of how fast it performs.

**What is Big-O**

Big-O means: as inputs grows, how much does your function slow down? As elements, input increases how many _operations_ does your function has to do?

- The slower it slows down, the better.
- Big O calculates the number of steps and calculations _NOT_ time it takes to run.

BIG O is important for big applications. Scalable code is thinking long term. Since we cannot pin down the exact runtime (in seconds) of an algorithms we measure how _quickly the runtime grows in relation to its input and as the input gets immensely large_.

Good developers make these decisions efficiently. Big-O can give us reliable data in terms of _Time Complexity_. At the end we'll discuss about Space Complexity as well.

As we drill down Big-O notations below, please refer to the [Big-O Cheatsheet](https://www.bigocheatsheet.com/) and to the graph below:

![Screen Shot 2020-06-18 at 7 29 26 PM](https://user-images.githubusercontent.com/15071636/85084334-1db98980-b19a-11ea-8b28-d5e2076dc251.png)

Remember we _cannot express speed in seconds_, so the size of the input we usually call it `n`. And the relationship with the algorithm so we could say for example our runtime grows lineally to the size of the input as O(n) or of the square of the size of the input as O(n^2). Let's go through each of these BigO examples.

### `O(n)` - Linear - PREFERRED

This is **linear**. As the number of elements increase so does the number of operations. Example:

```javascript
function myOwnIncludes(word, letter) {
  let includes;
  for (let i = 0; i < word.length; i++) {
    if (word[i] === letter) {
      includes = true;
    }
  }
  return !!includes;
}

myOwnIncludes("apple", "a");
```

### `O(1)` - Constant Time - EXCELLENT

With O(1) it will always be the same calculation no matter how big the input grows.

```javascript
function getFirstItem(box) {
  console.log(box[1]);
}
```

Note the 1 is arbitrary but this can be O(2), O(3) but do narrow it down to O(1) because to represent constant time. O(1) is used with Objects/Hash Tables data structures.

### `O(n^2)` - Nested Loops - BAD

If you see nested loops you it is O(n^2)! So the performance decreases n^2 as input grows not lineally.

**You get interview questions to make O(n^2) into an O(n) or better**. O(n^2) example:

```javascript
//Log all pairs of array

const boxes = ["a", "b", "c", "d", "e"];
function logAllPairsOfArray(array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      console.log(array[i], array[j]);
    }
  }
}
// nested loops so O(n^2)

logAllPairsOfArray(boxes);
```

### `O(n!)` - Factorial Time - MOST Expensive One

It means you add a nested loop for every input. You probably would never see it.

### `O(log n)` - EXCELLENT - Used in Tree Data Structures

There is a certain way to calculate number of nodes of perfect binary trees:

- You calculate 2 to the power of level in question.
  - E.g. Level 0: 2^0 = 1. Number of nodes: 1. Lvl 2: 2^2 = 4. etc.
  - Based on this formula you can do 2^treeHeight, to know how many total nodes. E.g. 3 Level Tree: 2^3 - 1 = 7 nodes.
  - We can simplify as **log notes = treeHeight**. So you by knowing this, you can limit steps by going in one branch.
  - So O(log n) is like **divide and conquer**. Choice of next element is one of several. We only choose one not all.
  - This like **looking through a phone book**. You look based upon the names you want. So **divide an conquer**. Only need to explore subset of tree.
  - Binary search trees allows us to search efficiently. Google uses this method too.

### `O(2^n)` Exponential time - PRETTY BAD - Worst Than O(n^2)

A classic example is the fibonacci with recursion:

```js
function fibonacci(num) {
  if (num <= 1) {
    return num;
  }

  return fibonacci(num - 2) + fibonacci(num - 1);
}
```

### `O(n log n)` - OK - Better than O(n^2) but worst than O(n)

- This performs better than others.
- **Divide and conquer: Merge sort and quick sort use this conquer along with recursion**.
- These **don't have nested loops**. See merge / quick sort for example.
- This O(n log n) is because it is still compared, everything at least once, but it is not compared everything to everything.

```javascript
// O(2^n)
function fibonacciRecursive(n) {
  if (n < 2) {
    return n;
  }
  return fibonacciRecursive(n - 1) + fibonacciRecursive(n - 2);
}

fibonacciRecursive(6);
```

## SIMPLIFYING BIG-O (BIG-O RULES)

1. **Worst Case**: Big-O cares at the worst case only.
   - Identify worst case. You could have O(1) but if O(n), then the Big-O is O(n).
2. **Remove Constants**.
   - Identify things that don't change and remove them.
   - E.g. you have two loops and so O(2n) but 2 is constant so it's actually O(n)
3. **Different terms for inputs**

```javascript
function compressBoxesTwice(box1, box2)
box1.forEach(b => {
       console.log(b)

})
box2.forEach(b => {
       console.log(b)

})
```

**This is actually O(a + b) NOT O(n)**. This because of different terms for inputs.

- If parallel loops you _ADD_. E.g. a + b
- If nested loops you _multiply_. E.g. a \* b

4. **Drop Non-Dominants**

```javascript
function printNumsThenAllPairSums(numbers) {
  console.log("these are the numbers:");
  numbers.forEach(function (number) {
    console.log(number);
  });

  console.log("and these are their sums:");
  numbers.forEach(function (firstNumber) {
    numbers.forEach(function (secondNumber) {
      console.log(firstNumber + secondNumber);
    });
  });
}

printNumsThenAllPairSums([1, 2, 3, 4, 5]);
```

- This could be as `O(n + n^2)`. But you need to drop non-dominants. n^2 is more important since it is worst. So drop `n` and it will be as `O(n^2)`.
- Worry about the MOST important then drop the rest.
- Focus on dominant terms.

### Space Complexity (Memory)

When program executes it will **heap** (store variables) or **stack** (keep track of function calls).
You also look at total size and see how much memory is being used.

What adds space complexity?

- Adding variables
- Adding data structures
- Function calls and allocations

Space complexity refers to additional space. Example:

```javascript
function boooo(n) {
  for (let i = 0; i < n; i++) {
    console.log("booooo");
  }
}

// Space complexity O(n)
function arrayOfHiNTimes(n) {
  var hiArray = [];
  for (let i = 0; i < n; i++) {
    hiArray[i] = "hi";
  }
  return hiArray;
}
```

Often it is a tradeoff of optimizing code it _will increase space complexity_.

## Final Notes

Sometimes optimizing might not be the right choice at beginning. Get the problem solved first. So you need to get the right balance between run time, space and readability. BigO is crucial for bigger apps but work on it, it will make you a better engineer. Focus on O(1), O(n) and O(n^2) then expand into others.

In interviews most of time you'll do O(n) and O(1)!

## Read More

- [**Understanding Big O Notation via JavaScript**](https://www.digitalocean.com/community/tutorials/js-big-o-notation)
- [**Master The Coding Interview**](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/)
- [**Understanding Big-O Notation With JavaScript**](https://dev.to/b0nbon1/understanding-big-o-notation-with-javascript-25mc)
