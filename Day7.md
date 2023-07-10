# Day 7: Closure

This README file summarizes the JavaScript lesson on closure.

## Lesson: Closure

In this lesson, we explore the concept of closure in JavaScript. Closure is an advanced and powerful concept that enables various functionalities and design patterns in JavaScript. Here are the key points covered in this lesson:

- Closure is a somewhat esoteric concept in JavaScript but has significant practical applications.
- Closure enables the creation of powerful functions like "once" and "memoize" that provide advanced functionality and optimization.
- Many JavaScript design patterns, including the module pattern, utilize closure to encapsulate and preserve state.
- Closure plays a crucial role in building iterators, handling partial application, and maintaining state in an asynchronous programming environment.
- Functions in JavaScript have their own memory or variable environment, which is created and destroyed upon each function invocation.
- Closure allows functions to hold onto live data or persistent memory between executions.
- Functions can be returned from other functions in JavaScript, leading to the concept of closure.
- The location where a function is defined determines its access to the surrounding local memory.
- When a function is defined, it forms a bond with the surrounding local memory, creating a closure or a "backpack" of data.
- The closure or backpack of data is attached to the function through a hidden property known as [[scope]].
- Each function has its own independent closure, allowing for encapsulated and persistent data.
- Closure finds applications in various scenarios, including professional helper functions, iterators and generators, the module pattern, and handling asynchronous JavaScript.

**Example: Closure in the Module Pattern**

```javascript
function outer() {
  let counter = 0;
  
  function incrementCounter() {
    counter++;
    console.log(counter);
  }

  return incrementCounter;
}

const myNewFunction = outer();
myNewFunction(); // Output: 1
myNewFunction(); // Output: 2

const anotherFunction = outer();
anotherFunction(); // Output: 1
anotherFunction(); // Output: 2

```
## Coding Exercises

### [Exercises for closures](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

#### My Solution
```javascript
Question 1:



```
