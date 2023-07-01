# Day 1: Introduction to JavaScript, DOM, Values & Data Types, and Operators

This README file summarizes the key concepts covered on Day 1 of my JavaScript learning journey. On this day, I explored the fundamentals of JavaScript, including an introduction to the language, the Document Object Model (DOM), values and data types, and operators. I also solved three coding exercises to practice my skills.

## Lesson Summary

In this lesson, I covered the following topics:

- Introduction to JavaScript: I learned about the basics of JavaScript as a programming language, its role in web development, and its wide range of applications.

- Document Object Model (DOM): I discovered the DOM, which represents the structure of HTML documents as a tree-like structure, allowing for dynamic manipulation and interaction with web pages using JavaScript.

- Values & Data Types: I explored the different types of values and data types in JavaScript, such as strings, numbers, booleans, null, undefined, and objects. I learned how to declare variables and assign values to them.

- Operators: I gained an understanding of various operators in JavaScript, including arithmetic operators for mathematical calculations, comparison operators for comparing values, and logical operators for combining conditions.

## Coding Examples

```javascript
// Example 1: Using console commands to find elements and text
console.log(document.querySelectorAll("p")); // Find all p elements
console.log(document.querySelector("#p1-symbol").textContent); // Find the text in element with id "p1-symbol"
console.log(document.querySelectorAll(".square").length); // Find the number of squares on the board
console.log(document.querySelector("h2").textContent); // Find the text in the h2 element

// Example 2: Editing webpage HTML using the console
document.querySelector("#p1-name").textContent = "Mohammad"; // Change player 1 name
document.querySelector("#p2-name").textContent = "ali"; // Change player 2 name
document.querySelector("#p1-symbol").textContent = "O"; // Swap player 1 symbol
document.querySelector("#p2-symbol").textContent = "X"; // Swap player 2 symbol
document.querySelector("h2").textContent = "A game you know and love"; // Change the subtitle

// Example 3: Determining value types using typeof
let value1 = "Hello";
let value2 = 42;
let value3 = true;
let value4 = null;
console.log(typeof value1); // string
console.log(typeof value2); // number
console.log(typeof value3); // boolean
console.log(typeof value4); // object (null is a special case)

// Example 4: String manipulation exercises
let myString = "Hello, world!";
console.log(myString.length); // Length of the string
console.log(myString.indexOf("world")); // Index of the first occurrence of "world"
console.log(myString.includes("Hello")); // Check if the string includes "Hello"
console.log(myString.toUpperCase()); // Convert the string to uppercase

// Example 5: Arithmetic operators
let x = 5;
let y = 3;
let addition = x + y; // Addition
let subtraction = x - y; // Subtraction
let multiplication = x * y; // Multiplication
let division = x / y; // Division
console.log(addition); // 8
console.log(subtraction); // 2
console.log(multiplication); // 15
console.log(division); // 1.6666666666666667

```
## Coding Exercises

### [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)

#### My Solution
```javascript
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;
```

### [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

#### My Solution
```javascript
let myStr ="This is the first sentence. ";
myStr += "This is the second sentence.";
```

### [Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)

#### My Solution
```javascript
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length-2]; // Change this line

```
