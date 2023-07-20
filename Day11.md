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
## STATIC TYPING QUESTIONS:
### QUESTION #1

Given the following `promisesArray`, convert the array into an object using the
`convertToObj` function.

You should apply typescript types to every promise, the input of `convertToObj`,
and the output of `convertToObj`. 

Build interfaces and types as needed.

```typescript

interface HelloWorldType {
    message: string;
  }
  
  interface CheckBooleanType {
    booleanValue: boolean;
  }
  
  interface ReturnObjType {
    x: string;
    y: number;
  }
  
  const sayHelloWorld: Promise<HelloWorldType> = new Promise(
    (resolve, reject) => {
      resolve({ message: "Hello world!" });
    }
  );
  
  const checkBoolean = (booleanValue: boolean): Promise<CheckBooleanType> =>
    new Promise((resolve, reject) => {
      if (booleanValue) {
        resolve({ booleanValue });
      } else {
        reject(`Input is false :(`);
      }
    });
  
  const returnObj: Promise<ReturnObjType> = new Promise((resolve, reject) => {
    resolve({ x: "meow", y: 45 });
  });
  
  const promisesArray: [
    Promise<HelloWorldType>,
    Promise<CheckBooleanType>,
    Promise<ReturnObjType>
  ]  = [sayHelloWorld, checkBoolean(true), returnObj];
  
  const convertToObj = (array: [
    Promise<HelloWorldType>,
    Promise<CheckBooleanType>,
    Promise<ReturnObjType>
  ]) => {
  
    return   Object.assign({}, array)
  };
  

  console.log(convertToObj(promisesArray))//Output : 
// {
//     '0': Promise { { message: 'Hello world!' }},
//     '1': Promise { { booleanValue: true }},
//     '2': Promise { { x: 'meow', y: 45 }}
// }


```

-------------------------------------------------------------------

## SCOPE & HOISTING QUESTIONS:

### QUESTION #1:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript
function testScope1() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a);
  console.log(b);
  console.log(c);
}

testScope1();

```
**Choices:**

A) `undefined`, `undefined`, `undefined`   
B) `1`, `undefined`, `ReferenceError`  
C) `1`, `ReferenceError`, `ReferenceError`   
`D)` `1`, `ReferenceError`

1. `var a = 1;` has function scope, so `a` will hold the value `1` when logged.
2. `let b = 2;` and `const c = 3;` have block scope, resulting in ReferenceError when logged outside the block.
-------------------------------------------------------------------

### QUESTION #2:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript
function testScope2() {
  console.log(a);
  console.log(b);
  console.log(c);
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
}

testScope2();

```

**Choices:**

`A)` `undefined`, `ReferenceError`   
B) `1`, `undefined`, `ReferenceError`   
C)`undefined`, `undefined`,
`ReferenceError`  
D) `1`, `ReferenceError`


1.  In JavaScript, `var` declarations are hoisted to the top of the function, so `a` is hoisted and initialized with `undefined` before being assigned the value `1` inside the block, resulting in `undefined` being printed to the console.
2. In JavaScript, variables declared with `let` and `const` are not hoisted, and they have block scope. When the `console.log(b)` statement is executed before the `if` block, `b` is accessed before its declaration, leading to a ReferenceError since it is not defined in that scope.
-------------------------------------------------------------------

### QUESTION #3:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript

function testScope3() {
  var a = 36;
  let b = 100;
  const c = 45;

  console.log([a, b, c]);

  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;

    console.log([a, b, c]);
  }

  console.log([a, b, c]);
}

testScope3();

```

**choices:**

A) `[ 36, 100, 45 ]` | `[ 1, 2, 3 ]` | `[ 36, 2, 3 ]`   
B) `[ 36, 100, 45 ]` | `[1, 2, 3 ]` | `[ 36, 100, 45 ]`   
`C)` `[ 36, 100, 45 ]` | `[ 1, 2, 3 ]` | `[ 1,100, 45 ]`   
D) `[ 36, 100, 45 ]` | `[ 1, 2, 3 ]` | `[ 1, 2, 3 ]`


1. The variables `a`, `b`, and `c` are declared using `var`, `let`, and `const` respectively.
2. After declaring these variables, the first `console.log()` statement outputs `[36, 100, 45]`, which is the initial values of `a`, `b`, and `c`.
3. Inside the `if (true)` block:
   - A new block-scoped `b` and `c` are declared and assigned the values `2` and `3`.
   - The `var a` is redeclared and reassigned the value `1`. However, due to hoisting, it affects the previous `var a` declared outside the block as well.
   - The second `console.log()` statement outputs `[1, 2, 3]`, which are the new values of `a`, `b`, and `c` inside the block.
4. After the block, the third `console.log()` statement outputs `[1, 100, 45]`, which is the new value of `a` from the block and the original values of `b` and `c` declared outside the block.

