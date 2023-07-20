# Day 10: Introduction and Types
this README file summarizes the JavaScript lesson on Introduction and Types covered in Day 10 of the course.
## Lesson 1: Introduction

In this lesson, we explored the importance of gaining a deep understanding of JavaScript. By developing a thorough understanding of the language, we can write more reliable and efficient code. Here are the key points covered in this lesson:

1. Significance of Deep Understanding: It is crucial to go beyond surface-level knowledge of JavaScript. Deep understanding allows us to uncover the intricacies and nuances of the language, helping us write code that is more robust and less prone to bugs.

2. Bugs and Incorrect Assumptions: Many bugs in JavaScript code arise from incorrect assumptions about how certain features or mechanisms work. By gaining a deep understanding, we can avoid these pitfalls and write code that behaves as expected.

3. Three Pillars of JavaScript: JavaScript can be divided into three main pillars, which form the foundation of the language:

   - Scope and Closures: Understanding how variables and functions are scoped in JavaScript, as well as how closures work, is essential for writing clean and maintainable code.
   
   - Prototypes and Objects: JavaScript is a prototype-based language, and understanding how prototypes work is crucial for effective object-oriented programming in JavaScript.
   
   - Types and Coercion: JavaScript has a dynamic and loosely typed nature. Understanding JavaScript's type system, including the behavior of various data types and type coercion, helps us write code that is both correct and performant.

## Lesson 2: Types

In this lesson, we explored JavaScript's type system and debunked the common misconception that everything in JavaScript is an object. Here are the key points covered in this lesson:

1. The `typeof` Operator: The `typeof` operator is used to determine the type of a value in JavaScript. We examined its behavior and discussed cases that can be misleading, such as the `typeof null` returning "object" and `typeof` arrays returning "object".

2. BigInt: JavaScript introduced the `BigInt` type to handle integers that exceed the maximum safe integer value. We explored the purpose of `BigInt` and learned how it differs from other number types.

3. Empty Values: JavaScript provides different ways to represent empty or non-existent values, including `undefined`, undeclared variables, and uninitialized variables. We examined each case and understood their implications.

4. NaN: `NaN` stands for "Not-a-Number" and represents an invalid or unrepresentable numeric value. We discussed the concept of `NaN`, learned how to use the `isNaN` function to check for `NaN`, and identified common pitfalls in its usage.

5. Handling -0: JavaScript supports negative zero, denoted as `-0`. We explored the behavior of `-0` in calculations and discussed situations where it can lead to unexpected results.

6. The `Object.is` Method: JavaScript provides the `Object.is` method to compare two values for equality, including special cases like `NaN` and `-0`. We learned how `Object.is` differs from the strict equality (`===`) operator and understood when to use it.

Throughout the lesson, we provided code examples and explanations to solidify our understanding of JavaScript's type system.

## Coding Example:

```javascript
const age = 22;
const name = "Mohammad";
const isStudent = false;
const hobbies = ["reading", "painting", "gaming"];

console.log(typeof age); // Output: "number"
console.log(typeof name); // Output: "string"
console.log(typeof isStudent); // Output: "boolean"
console.log(typeof hobbies); // Output: "object"

const result1 = 10 / "apple";
const result2 = parseInt("banana");

console.log(isNaN(result1)); // Output: true
console.log(isNaN(result2)); // Output: true

console.log(Object.is(1, 1)); // Output: true
console.log(Object.is(NaN, NaN)); // Output: true
console.log(Object.is(0, -0)); // Output: false
console.log(Object.is({}, {})); // Output: false
```
## Coding Exercises

### Question 1:

Write a function called `convertStringToNumber` that converts a string to a
number using the unary plus operator. 

If the input is not a string, return an object of the input's value and type.

```javascript

function convertStringToNumber(input) {
  return typeof input === "string"
    ? +input
    : { value: input, type: typeof input };
}
console.log("12"); //Output : 12
console.log(convertStringToNumber(false)); //Output : { value: false, type: 'boolean' }

```

-------------------------------------------------------------------

### Question 2:

Write a function called `checkNaN` that takes a single argument and returns
`true` if the argument is `NaN` and `false` otherwise. 

```javascript
const checkNaN = (value) => {
  return isNaN(value);
};
console.log(checkNaN(10)); //Output : false
console.log(checkNaN("asd")); //Output : true

```

-------------------------------------------------------------------

### Question 3: 

Write a function called `isEmptyValue` that checks if a given input is an empty value (undefined,
null, or empty string). 

```javascript
function isEmptyValue(value) {
  return value ? false : true;
}
console.log(isEmptyValue(2)); //Output : false
console.log(isEmptyValue(undefined)); //Output : true
console.log(isEmptyValue(null)); //Output : true
console.log(isEmptyValue("")); //Output : true

```

-------------------------------------------------------------------

### Question 4: 

Write a function called `compareObjects` that takes 2 arguments of type
`"object"` and compares them. If both arguments are equal, return `true`. If
not, return `false`.

If either argument is not of type `"object"`, the function should return an
array of the arguments. 

```javascript
function compareObjects(input1, input2) {
  if (typeof input1 !== "object" || typeof input2 !== "object") {
    return [input1, input2];
  }
  if (Object.keys(input1).length !== Object.keys(input2).length) {
    return false;
  }
  for (const key of Object.keys(input1)) {
    if (!Object.keys(input2).includes(key) || input1[key] !== input2[key]) {
      return false;
    }
  }
  return true;
}
console.log(compareObjects({ 1: "meo", 2: "hello" }, { 1: "meo", 2: "hello" })); //Output :true
console.log(compareObjects({ 1: "meo", 2: "hi" }, { 1: "meo", 2: "hello" })); //Output :false
console.log(compareObjects({}, {})); //Output :true
console.log(compareObjects({ 1: "meo", 2: "hi" }, 44)); //Output :[ { '1': 'meo', '2': 'hi' }, 44 ]

```

-------------------------------------------------------------------

### Question 5: 

Write a function called `complexCoercion` that takes a single argument and
checks if its type is primitive, and if so returns a coerced value according to
the rules below.

coercion rules: 
- if input is primive and:
  - if input is a number, convert to string and then return a boolean. 
  - if input is a string, return a boolean.
  - if input is `null` or `undefined`, return `false`.

If input is not a primitive type, return the argument.

```javascript
const complexCoercion = (input) => {
  if (typeof input === "number") {
    return Boolean(String(input));
  }

  if (typeof input === "string") {
    return Boolean(input);
  }

  if (typeof input === "undefined" || input === null) {
    return false;
  }
  return input;
};
console.log(complexCoercion(42)); //Output :true
console.log(complexCoercion("hello meoshan")); //Output :true
console.log(complexCoercion(undefined)); //Output :false
console.log(complexCoercion({})); //Output :{}

```
