# Day 13: Advanced Scope and Closure

This README file summarizes the JavaScript lessons on Advanced Scope and Closure.

## Lesson 1: Advanced Scope - the remaining 30 mins

In this lesson, we delve further into scope-related concepts, specifically focusing on the remaining aspects of `const`, hoisting, and the behavior of variables in JavaScript. Here are the key points covered in this lesson:

### `const` and Semantic Issues

`const` is used for variable declarations that should remain constant and not be reassigned. While it ensures immutability, it can lead to potential semantic issues when dealing with objects and arrays. Although the variable itself cannot be reassigned, its properties can be modified.

```javascript
const myObj = { value: 10 };
myObj.value = 20; // No error, value can be modified
```

### Hoisting and Myth Debunking

Hoisting refers to the behavior of moving function and variable declarations to the top of their scope during the compilation phase. This allows functions to be called before they appear in the code.

```javascript
console.log(myFunc()); // Output: "Hello, World!"

function myFunc() {
  return "Hello, World!";
}
```

Contrary to popular belief, both `var` and `let` variables hoist. The key difference is that `var` variables are initialized with `undefined`, while `let` variables are in the "temporal dead zone" before their declaration.

### Refactoring with Hoisting

Refactoring code to take advantage of hoisting can improve readability. For example, when working with multiple functions, hoisting function declarations can make the code more concise.

```javascript
function doSomething() {
  return myFunction();

  function myFunction() {
    return "Something";
  }
}
```

## Lesson 2: Closure

In this lesson, we explore the powerful concept of closure in JavaScript and its connection to functional programming languages. Closure allows functions to retain access to variables from their containing (enclosing) scope even after that scope has finished executing. Here are the key points covered in this lesson:

### Understanding Closure

Closure involves a function closing over variables from its outer scope. This enables the function to retain access to those variables, even if they are not directly accessible from outside the function.

```javascript
function createCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const counter = createCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
```

In this example, the inner function retains access to the `count` variable from the `createCounter` function, forming a closure.

### The Module Pattern and Data Encapsulation

The module pattern utilizes closure to create private data and expose a public API for interacting with that data. This is particularly useful for encapsulating data and preventing unwanted modifications.

```javascript
const counterModule = (function () {
  let count = 0;

  return {
    increment() {
      count++;
    },
    decrement() {
      count--;
    },
    getCount() {
      return count;
    },
  };
})();
```
## Coding Exercises

## ADVANCED SCOPE:

### QUESTION #1

Given the following code snippet and **explain what's happening**.

```javascript
for (var i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log("value of [i] is: ", i);
    }, 100);
}
```

The current output is: "value of [i] is: 5" five times.

The output should be: 

"value of [i] is: ", 0 "value of [i] is: ", 1 "value of [i] is: ", 2 "value of
[i] is: ", 3 "value of [i] is: ", 4

Without changing anything in the for loop's code itself, provide a solution to
fix it.
### My solution 
The reason for the current output of "value of [i] is: 5" being printed five times is due to the concept of closures and how `var` behaves in JavaScript. When the `setTimeout` callback function is executed, it captures the reference to the variable `i`, which is defined using `var`. Since `var` has function scope and is hoisted, by the time the `setTimeout` callbacks are executed after the loop finishes, the value of `i` is 5 (the value that caused the loop to exit).

To fix this and get the desired output, we need to create a new scope for each iteration of the loop to capture the value of `i` correctly. One way to achieve this is by using the `let` keyword instead of `var`, as `let` has block scope and behaves differently with closures.

Here's the fixed code using `let`:

```javascript
for (let i = 0; i < 5; i++) {
  setTimeout(function() {
    console.log("value of [i] is: ", i);
  }, 100);
}
```

Explanation:
1. By using `let i` instead of `var i`, each iteration of the loop will create a new block-scoped `i`, and the `setTimeout` callback function will capture the correct value of `i` for each iteration.
2. As a result, the desired output will be:
```
"value of [i] is: " 0
"value of [i] is: " 1
"value of [i] is: " 2
"value of [i] is: " 3
"value of [i] is: " 4
```
Each value of `i` is captured correctly because of the block-scoping behavior of `let`.

-------------------------------------------------------------------

## ADVANCED SCOPE:

### QUESTION #2

Given the following code snippet and **explain what's happening**. 

```javascript

for (let i = 0; i < 5; i++) {
   let array = [];
   array.push(i);
   console.log("Current array is: ", array)
}

```

The current output is: 

"Current array is: [ 0 ]" "Current array is: [ 1 ]" "Current array is: [ 2 ]"
"Current array is: [ 3 ]" "Current array is: [ 4 ]".

The output should be: "Current array is: [0, 1, 2, 3, 4]".

Provide a solution to fix it. 
### My solution
The reason for the current output is that the `array` is being redeclared and reinitialized in each iteration of the loop. This means that in each iteration, a new empty array is created, and only the current value of `i` is pushed into that array. Hence, the console prints the array with one element corresponding to the current value of `i`.

To fix this and get the desired output, we need to move the declaration and initialization of the `array` outside the loop so that the array remains in scope and retains its values across iterations.

Here's the fixed code:

```javascript
let array = [];
for (let i = 0; i < 5; i++) {
  array.push(i);
}
console.log("Current array is: ", array);

```

Explanation:
1. By declaring `array` outside the loop using `let`, it remains in scope for the entire loop, and its values are retained across iterations.
2. In each iteration, the current value of `i` is pushed into the same `array` using `array.push(i)`.
3. The desired output will be:
```
Current array is:  [ 0, 1, 2, 3, 4 ]
```
-------------------------------------------------------------------

## ADVANCED SCOPE:

### QUESTION #3

Given the following code snippet and **explain what's happening**. 

```javascript

let functions = [];

for (var i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());

```

The current output is: 

"Current value of i is: 5" "Current value of i is: 5" "Current value of i is: 5"
"Current value of i is: 5" "Current value of i is: 5"

The output should be: 

"Current value of i is: 0" "Current value of i is: 1" "Current value of i is: 2"
"Current value of i is: 3" "Current value of i is: 4"

Provide a solution to fix it. 
### My solution 
The reason for the current output is that the arrow function `() => {...}` inside the loop is capturing the variable `i` by reference, not by value. When the `forEach` loop is executed, all the arrow functions in the `functions` array reference the same variable `i`, which has the final value of `5` after the loop exits.

To fix this and get the desired output, we need to use `let` instead of `var` to declare `i`. This way, each iteration of the loop will have its own block-scoped `i`, and the arrow functions will capture the correct value of `i` for each iteration.

Here's the fixed code using `let`:

```javascript
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```

Explanation:
1. By using `let i` instead of `var i`, each iteration of the loop will create a new block-scoped `i`, and the arrow function `() => {...}` will capture the correct value of `i` for each iteration.
2. In each iteration, a new arrow function is pushed into the `functions` array, and each arrow function captures the corresponding value of `i`.
3. The desired output will be:
```
"Current value of i is: 0"
"Current value of i is: 1"
"Current value of i is: 2"
"Current value of i is: 3"
"Current value of i is: 4"
```
Each arrow function correctly logs the value of `i` captured during its respective iteration. The block-scoping behavior of `let` ensures that the captured value of `i` is not affected by subsequent iterations.

-------------------------------------------------------------------

## CLOSURE:

### QUESTION #1

Create a function called `privateCounter()` that behaves like a private counter.
The function should not have any public variables, and the count should only be
accessible through a closure. It should have two methods: `increment()` and
`getCount()`. The `increment()` method should increment the count, and
`getCount()` should return the current count.

### My solution
```javascript
const privateCounter = () => {
  let count = 0;

  const increment = () => {
    count++;
  };

  const getCount = () => {
    return count;
  };

  return {
    increment,
    getCount,
  };
};
const counter = privateCounter();
console.log(counter.getCount()); // Output: 0
counter.increment();
counter.increment();
counter.increment();
console.log(counter.getCount()); // Output: 3

```
-------------------------------------------------------------------

## CLOSURE:

### QUESTION #2

Write a JavaScript function called `generateFibonacci(count)` that returns a
closure. The closure should generate the next number in the Fibonacci sequence
each time it is called. The `generateFibonacci` function should take a parameter
`count` that determines how many times the closure will generate the next
number, and it should use recursion for this purpose.

### My solution
```javascript

const generateFibonacci = (count) => {
  let currentCount = 0;

  const fibonacciGenerator = (currentNumber, nextNumber) => {
    if (currentCount < count) {
      currentCount++;
      const temp = currentNumber;
      console.log(temp);
      return fibonacciGenerator(nextNumber, currentNumber + nextNumber);
    } else {
      return undefined;
    }
  };

  return () => fibonacciGenerator(0, 1);
};
const fibonacciClosure = generateFibonacci(20);
fibonacciClosure();

```
