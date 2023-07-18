# Day 11: Static Typing and Scope

This README file summarizes the JavaScript lessons on Static Typing and Scope.

## Lesson 1: Static Typing

In this lesson, we explore the concept of static typing in JavaScript and discuss its benefits and drawbacks. Static typing involves specifying the types of variables and parameters at compile-time, allowing for type checking before code execution. This helps catch potential type errors and improves code reliability. Here are the key points covered in this lesson:

- Introduction to tools like TypeScript and Flow that enable static type checking in JavaScript. These tools provide a way to annotate variables and functions with type information, enabling early detection of type-related errors during development.
- Understanding type inference, where the compiler automatically infers the types based on the assigned values. This helps reduce the need for explicit type annotations in many cases, making code more concise and readable.
- Defining custom types using type annotations to create structured and predictable data shapes. Custom types allow developers to define their own data structures with specific properties and enforce type safety.
- Exploring the validation of operand types as a useful aspect of static typing. By specifying the expected types of operands, static typing can catch potential errors caused by incompatible types.
- Comparing TypeScript and Flow, two popular static typing tools. Both tools offer similar functionality, but they differ in terms of syntax, ecosystem, and integration with existing JavaScript codebases.
- Discussing the benefits of static typing, such as improved code readability, easier maintenance, enhanced developer productivity, and increased confidence in code correctness.
- Discussing the drawbacks of static typing, including potential overhead in terms of development time, the need to learn additional syntax and tools, and the possible trade-off between flexibility and strictness.

### Example 1: Custom Types

```javascript
// Custom type: Person
type Person = {
  name: string;
  age: number;
  email: string;
};

function sendEmail(person: Person, message: string) {
  console.log(`Sending email to ${person.name} (${person.email}): ${message}`);
}

const user: Person = {
  name: 'John Doe',
  age: 25,
  email: 'john.doe@example.com',
};

sendEmail(user, 'Hello! This is a test email.');
```


### Example 2: Type Validation

```javascript
function multiply(a: number, b: number): number {
  return a * b;
}

const result: number = multiply(5, 10);
console.log(result); // Output: 50

```


## Lesson 2: Scope

In this lesson, we delve into the concept of scope in JavaScript, which determines the visibility and accessibility of variables throughout the code. Understanding scope is crucial for managing variable lifetime, avoiding conflicts, and writing maintainable code. Here are the key points covered in this lesson:

- Introduction to the compilation and execution stages of JavaScript code. During compilation, the JavaScript engine sets up the scope, while execution runs the code within the defined scope.
- Walking through the compilation stage using a mental model for scope. This mental model involves two stages: lexical scope and dynamic scope. Lexical scope is determined by the placement of variables and functions in the source code, while dynamic scope is based on the call stack at runtime.
- Differentiating between compilation and execution of code. Compilation involves the creation of the scope and the mapping of variables to memory, while execution involves running the code within the defined scope and accessing the variables.
- Understanding lexical scope, also known as static scope, where the scope is determined by the structure of the code at the time of definition. Lexical scoping allows variables and functions to be accessed within their containing scope and any nested scopes.
- Exploring dynamic global variables, which are created when variables are assigned without declaring them with the `var`, `let`, or `const` keywords. Dynamic global variables can cause unexpected behavior and should be avoided.
- Presenting arguments for using strict mode in JavaScript, a stricter variant that helps catch common coding mistakes and enforces best practices. Strict mode prevents the use of undeclared variables and eliminates certain JavaScript silent errors.
- Walking through an example of nested scope, where functions are defined inside other functions. Inner functions have access to variables in their outer functions, creating a hierarchical scope chain.
- Reviewing the difference between an undefined variable, which exists but has no assigned value, and an undeclared variable, which is referenced without being previously declared.

### Example 1: Nested Scope

```javascript
function outer() {
  const outerVariable = 'Outer';

  function inner() {
    const innerVariable = 'Inner';
    console.log(innerVariable); // Output: Inner
    console.log(outerVariable); // Output: Outer
  }

  inner();
}

outer();
```
## Coding Exercises
### [SECTION'S EXERCISES](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)
