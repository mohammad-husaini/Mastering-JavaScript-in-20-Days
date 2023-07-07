# Day 5: Data Fetching, Promises, Destructuring, Async, and Modules

This README file summarizes the JavaScript lessons on data fetching, promises, destructuring, async functions, and modules.

## Lesson 1: Data Fetching & Promises

In this lesson, we explore fetching data from an API endpoint using the `fetch` function and working with promises. Here are the key points covered in this lesson:

- Using the `fetch` function to load data from an API endpoint.
- Understanding the states of a promise: pending, fulfilled, and rejected.
- Using the `await` operator to wait for a promise and obtain its resulting value.

**Example: Fetching Data**

```javascript
async function fetchData(url) {
  const response = await fetch(url);
  const data = await response.json();
  return data;
}

const apiUrl = "https://api.example.com/data";
const result = await fetchData(apiUrl);
console.log(result);
```

## Lesson 2: Destructuring Data

Destructuring allows us to declare multiple variables at once by extracting values from objects or arrays. Here are the key points covered in this lesson:

- Destructuring objects to retrieve values from properties.
- Destructuring arrays using square brackets.
- Applying destructuring in various scenarios to simplify code.

**Example: Destructuring Objects**

```javascript
const person = {
  name: "Mohammad Husaini",
  age: 21,
  city: "Hebron",
};

const { name, age } = person;
console.log(name); // Output: "Mohammad Husaini"
console.log(age); // Output: 21
```

## Lesson 3: Async Functions

Async functions provide a cleaner syntax for writing asynchronous code. Here are the key points covered in this lesson:

- Combining async fetching and parsing into a single function.
- Using the `await` keyword to retrieve the contents of a returned promise.
- Handling errors and exceptions in async functions.

**Example: Async Function**

```javascript
async function fetchData(url) {
  try {
    const response = await fetch(url);
    const data = await response.json();
    return data;
  } catch (error) {
    console.error(error);
    throw new Error("An error occurred while fetching data.");
  }
}

const apiUrl = "https://api.example.com/data";
try {
  const result = await fetchData(apiUrl);
  console.log(result);
} catch (error) {
  console.error(error);
}
```

## Lesson 4: Modules

Modules allow us to split large codebases into smaller files for better organization and reusability. Here are the key points covered in this lesson:

- Understanding the differences between JavaScript and module JavaScript.
- Importing and exporting modules using the `import` and `export` keywords.
- Debugging and error handling techniques.

**Example: Module Imports and Exports**

```javascript
// Module 1: math.js
export function add(a, b) {
  return a + b;
}

// Module 2: utils.js
export function capitalize(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

// Main file: main.js
import { add } from "./math.js";
import { capitalize } from "./utils.js";

console.log(add(2, 3)); // Output: 5
console.log(capitalize("hello")); // Output: "Hello"
```

## Coding Example

```html

</html>
```
## Coding Exercises

### [Build a Rick & Morty characters list](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)

#### My Solution
```javascript

```
