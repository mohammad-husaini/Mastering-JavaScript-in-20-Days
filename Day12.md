# Day 12: Scope and Function Expressions

This README file summarizes the JavaScript lessons on Scope and Function Expressions.

## Lesson 1: Scope and Function Expression

In this lesson, we delve into the concept of scope in JavaScript and explore function expressions. Here are the key points covered in this lesson:

- Understanding scope and its impact on variable visibility and access within functions.
- Analyzing function expressions and their relation to scope.
- Advantages of using named function expressions over anonymous function expressions.
- Drawbacks of arrow functions and their use cases.
- Introducing a hierarchy of function types based on previous lessons.
- Practical exercises to write comparable functions and function expressions.
- Live coding examples using function declarations and arrow functions.

### Function Expressions and Scope

Function expressions in JavaScript are defined using variable assignments. These expressions can either be named or anonymous. Named function expressions have several advantages over anonymous ones, such as improved stack traces and self-reference. It's essential to understand how scope affects the visibility and accessibility of variables within functions and function expressions.

### Arrow Functions

Arrow functions are a concise way to define functions in JavaScript, but they also have some drawbacks. One of the main issues is the lexical binding of `this`, which can cause confusion in certain scenarios. We explore when and when not to use arrow functions based on their specific use cases.

### Hierarchy of Function Types

To better comprehend function expressions and their scope, we establish a hierarchy of function types. This classification helps us categorize functions based on their characteristics and use cases, providing a deeper understanding of their behavior.

## Lesson 2: Advanced Scope - First 40 Minutes

In this lesson, we further explore the intricacies of scope in JavaScript, distinguishing between lexical scoping and dynamic scoping. Here are the key points covered in this lesson:

- Contrasting lexical scoping and dynamic scoping models, providing examples of each.
- Techniques to conceptualize lexical scope, including the bucket model and type highlighting tool.
- Demonstrating dynamic scope with a theoretical code example.
- Advantages of strategically hiding information through scope levels.
- Benefits of using Immediately Invoked Function Expressions (IIFE) as a scoping pattern.
- Differentiating between situations where block scoping with `let` or `var` is useful.
- Presenting a use case for an explicit `let` block to create block scoping.

### Lexical Scoping vs. Dynamic Scoping

We examine the differences between lexical scoping, where variables are bound based on the code's structure, and dynamic scoping, which resolves variables based on the runtime call stack. Understanding these models is crucial for writing maintainable and predictable code.

### Techniques for Lexical Scope

To better grasp lexical scope, we introduce additional techniques such as the bucket model and a type highlighting tool. These approaches aid in visualizing and reasoning about the flow of data and variables within different scopes.

### Strategically Hiding Information

Scope allows us to control the visibility of variables and functions, strategically hiding information to prevent unwanted access and potential conflicts. We explore the core principle of scope as a tool for information management.

### IIFE and Block Scoping

Immediately Invoked Function Expressions (IIFE) offer a way to create enclosed scopes for modular and self-contained code. We discuss the advantages of using IIFE as a scoping pattern.

### Choosing Between `let` and `var`

The choice between `let` and `var` depends on various factors, including performance and code communication. We analyze scenarios where each declaration type is most appropriate.

## Code examples

### Example 1: Named Function Expression

```javascript
// Named Function Expression
const add = function sum(a, b) {
  return a + b;
};

console.log(add(2, 3)); // Output: 5

// Accessing the function name 'sum' inside the function
console.log(add.name); // Output: "sum"
```

### Example 2: Arrow Function

```javascript
// Arrow Function
const multiply = (a, b) => a * b;

console.log(multiply(2, 3)); // Output: 6

// 'this' is lexically scoped in arrow functions
const person = {
  name: "Mohammad",
  greet: () => {
    console.log(`Hello, I'm ${this.name}`); // Output: "Hello, I'm undefined"
  },
};

person.greet();
```

### Example 3: IIFE (Immediately Invoked Function Expression)

```javascript
// IIFE (Immediately Invoked Function Expression)
(function () {
  const message = "Hello from IIFE!";
  console.log(message); // Output: "Hello from IIFE!"
})();

// IIFE with arguments
(function (a, b) {
  console.log(a + b); // Output: 5
})(2, 3);
```

### Example 4: Block Scoping with `let`

```javascript
// Block Scoping with let
function printNumbers() {
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }

  // 'i' is not accessible outside the block
  // console.log(i); // Throws an error
}

printNumbers();
```

### Example 5: Lexical Scoping vs. Dynamic Scoping

```javascript
// Lexical Scoping
function outer() {
  const message = "Hello from outer!";

  function inner() {
    console.log(message); // Output: "Hello from outer!"
  }

  inner();
}

outer();

// Dynamic Scoping (Not Supported in JavaScript)
function dynamicScope() {
  console.log(message); // Output: "Hello from outer!" (if dynamic scoping was supported)
}

function outer() {
  const message = "Hello from outer!";
  dynamicScope();
}

outer();
```

