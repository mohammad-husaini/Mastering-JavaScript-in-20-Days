# Day 6: JavaScript Principles, Callbacks & Higher Order Functions

This README file summarizes the JavaScript lessons on JavaScript principles, callbacks, and higher-order functions.

## Lesson 1: JavaScript Principles

In this lesson, we explore important principles of JavaScript that form the foundation of the language. Some key points covered in this lesson are:

- Code Traversal: JavaScript code runs line-by-line, executing each line known as the thread of execution. It saves data and functions in its memory.
- Execution Context: JavaScript keeps track of the currently running function using execution contexts. Functions are defined and can be executed later.
- Call Stack: The call stack helps JavaScript keep track of the function currently being executed. Functions are added to the call stack and removed when finished.

**Example: Code Traversal**

```javascript
const num = 3;

function multiplyBy2(inputNumber){
  const result = inputNumber * 2;
  return result;
}

const output = multiplyBy2(num);
const newOutput = multiplyBy2(10);
```

## Lesson 2: Callbacks & Higher Order Functions

The second lesson focuses on callbacks and higher-order functions in JavaScript. These concepts allow us to write more versatile and reusable code. Some key points covered in this lesson include:

- Higher Order Functions: Functions that accept other functions as parameters or return functions as values. They enable writing reusable and efficient code by separating concerns.
- Callback Functions: Functions passed as arguments to other functions. They are called by the higher-order function to perform a specific operation.
- Advantages of Callbacks: Callbacks improve code readability, enable declarative programming, and are crucial for asynchronous JavaScript operations.

**Example: Higher Order Function with Callback**

```javascript
function copyArrayAndManipulate(array, instructions) {
  const output = [];
  for (let i = 0; i < array.length; i++) {
    output.push(instructions(array[i]));
  }
  return output;
}

function multiplyBy2(input) {
  return input * 2;
}

const result = copyArrayAndManipulate([1, 2, 3], multiplyBy2);
```

The above example demonstrates a higher-order function, `copyArrayAndManipulate`, that accepts an array and an instructions function as parameters. The function iterates over the array and applies the instructions function to each element. In this case, the instructions function is `multiplyBy2`.

## Coding Exercises

### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

#### My Solution
```javascript
const squareList = (arr) => {
  // Only change code below this line
  return arr.filter((e) => Number.isInteger(e) && e >= 0).map(e=>Math.pow(e,2));
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);

```

## Coding Exercises

### [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

#### My Solution
```javascript
// Only change code below this line
function urlSlug(title) {
  return title
    .toLowerCase()
    .split(" ")
    .filter((e) => e !== "")
    .join("-");
}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```

## Coding Exercises

### [Exercises for functions and callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)

#### My Solution
```javascript
Question 1: Functions and Callbacks

function mapAsync(arr, callback) {
  return new Promise((resolve, reject) => {
    resolve(arr.map((e) => callback(e)));
    reject((error) => console.log(error));
  });
}


Question 2: Call Stack and Recursion

const sumRange = (start, end) => {
  if (start === end) {
    return start;
  }
  if (start > end) {
    return console.log("Error");
  } else {
  }
  {
    return start + sumRange(start + 1, end);
  }
};
console.log(sumRange(3, 7)); // Output: 25

```
