# Day 2: Expressions, Arrays, and Objects

This README file summarizes the JavaScript lessons on expressions, arrays, and objects. We explore how to work with expressions to obtain values, manipulate arrays, and create and manipulate objects.

## Lesson 1: Expressions

Expressions are a fundamental concept in JavaScript. Here are the key points covered in this lesson:

- An expression is a valid set of literals, variables, and operators that resolves to a single value.
- JavaScript allows us to remember values by declaring and assigning them as variables.
- The `let` and `const` keywords are used to declare variables, and they have different behaviors.
- JavaScript evaluates expressions based on the order of operations and resolves them to a value.
- Statements are different from expressions, as statements instruct JavaScript to perform actions.

## Lesson 2: Arrays

Arrays are used to store multiple values in a single variable. Here are the key points covered in this lesson:

- Arrays are collections of items, and each item is stored at an index.
- We can access array items using their index and determine the length of an array using the `.length` property.
- Array methods such as `sort`, `join`, and `concat` can be used to manipulate arrays.
- Some array methods mutate the original array, while others create a new copy without modifying the original array.
- Immutable data and variables are preferred to avoid unintended data mutations.

## Lesson 3: Objects

Objects are used to represent complex data structures in JavaScript. Here are the key points covered in this lesson:

- Objects store data in key-value pairs, where the key is a string (or symbol) and the value can be any data type.
- We can access object properties using dot notation or bracket notation.
- Objects can have properties that point to functions, known as methods.
- Nested objects and objects within arrays are common in JavaScript.
- JavaScript provides predefined objects like `document`, `console`, `Math`, and `String`, which have built-in methods.


## Coding Examples

```javascript
// Example 1: Declaring and Assigning Variables
let name = "Mohammad";
const parentsAge = 50 + 45;
const boardElement = document.querySelector("#board");

// Example 2: Manipulating Arrays
const numbers = [1, 2, 3, 4, 5];

// Accessing array items
console.log(numbers[0]); // Output: 1

// Modifying array items
numbers[2] = 10;
console.log(numbers); // Output: [1, 2, 10, 4, 5]

// Array methods
const sortedNumbers = numbers.sort();
console.log(sortedNumbers); // Output: [1, 10, 2, 4, 5]

const joinedNumbers = numbers.join("-");
console.log(joinedNumbers); // Output: "1-10-2-4-5"

const concatenatedNumbers = numbers.concat([6, 7, 8]);
console.log(concatenatedNumbers); // Output: [1, 10, 2, 4, 5, 6, 7, 8]

// Example 3: Creating and Accessing Objects
const person = {
  name: "Mohammad Husaini",
  age: 21,
  isStudent: false,
};

console.log(person.name); // Output: "Mohammad Husaini"
console.log(person["age"]); // Output: 21
```
## Coding Exercises

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

#### My Solution
```javascript
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line
  for (let index = 0; index < contacts.length; index++) {
    if (contacts[index].firstName === name) {
      return contacts[index][prop] ? contacts[index][prop] : "No such property";
    }
  }
  return "No such contact";
  // Only change code above this line
}

lookUpProfile("Akira", "likes");


```
### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

#### My Solution
```javascript
function forecast(arr) {
  // Only change code below this line

  return arr.slice(2, 4);
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));

```
### [Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

#### My Solution
```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence = ['learning',...fragment,'is','fun']; // Change this line
  return sentence;
}

console.log(spreadOut());

```


