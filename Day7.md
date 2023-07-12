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

const createCounter = (start) => {
  let counter = start;
  const incrementCounter = () => counter++;
  return incrementCounter;
};
const incCounter = createCounter(3);

console.log(incCounter()); // Output: 3
console.log(incCounter()); // Output: 4
console.log(incCounter()); // Output: 5
console.log(incCounter()); // Output: 6

Question 2:

const calculateAverage = (arr) => {
  const average = () => arr.reduce((a, b) => a + b) / arr.length;
  return average;
};
const arrAvg = calculateAverage([3, 8, 13]);
console.log(arrAvg()); //Output : 8

Question 3:

const powerOf = (base) => {
  let power = null;
  const pow = (exp) => (power = Math.pow(base, exp));
  return pow;
};
const powerOfNumber = powerOf(2);
console.log(powerOfNumber(5)); //Output : 32

Question 4:

function compose(...functions) {
  const functionsRevers = (functionResult) => {
    let result = functionResult;
    for (let i = functions.length - 1; i >= 0; i--) {
      result = functions[i](result);
    }
    return result;
  };

  return functionsRevers;
}
const addX = (x) => x + 1;
const minX = (x) => x - 3;
const multiY = (x) => x * 2;
const functionReverseOrder = compose(addX, minX, multiY);
console.log(functionReverseOrder(5)); //output : 8

```
