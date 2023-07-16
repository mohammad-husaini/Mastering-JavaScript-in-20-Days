# Day 8: Asynchronous JavaScript and Promises

This README file summarizes the JavaScript lessons on Asynchronous JavaScript and Promises covered in Day 8 of the course.

## Lesson 1: Asynchronous JavaScript

In this lesson, we dive into the world of asynchronous JavaScript, which is essential for building dynamic web applications. Here's an overview of the topics covered:

1. Introduction to Asynchronicity:
   - Understanding the execution model of JavaScript as single-threaded and synchronous.
   - Exploring the need for asynchronicity to handle long-running tasks without blocking other code execution.

2. Web Browser APIs and Background Features:
   - Introducing web browser or Node background APIs, including timers like `setTimeout`, promises, and the event loop.
   - Understanding how these additional features enable asynchronous behavior in JavaScript.

3. Facade Functions:
   - Exploring "facade functions" provided by JavaScript that act as interfaces to interact with browser features.
   - Examples of facade functions include `console`, `fetch`, `document`, and `setTimeout`.
   - Discussing how these functions enable communication with underlying web browser APIs.

4. `setTimeout` and Asynchronous Execution:
   - Examining the `setTimeout` function in detail, including its mechanics and how it fits into JavaScript's single-threaded nature.
   - Understanding the order of execution when `setTimeout` is used alongside synchronous operations.

5. Callback Queue and Event Loop:
   - Introducing the concept of a callback queue and the event loop to handle asynchronous code execution.
   - Explaining how the event loop manages the call stack and callback queue to ensure proper execution order.

6. Challenges with Web Browser APIs:
   - Addressing challenges associated with using web browser APIs in conjunction with callback functions.
   - Discussing common issues such as callback hell and strategies for organizing and maintaining readable code.

#### Example: Using `setTimeout` for Delayed Execution

```javascript
function printHello() {
  console.log("Hello");
}

setTimeout(printHello, 1000);
console.log("Me first!");
```

In this example, the `printHello` function is scheduled to execute after a delay of 1000 milliseconds using `setTimeout`. Meanwhile, the code continues to execute, and "Me first!" is logged to the console immediately. After the delay, "Hello" is logged.

## Lesson 2: Promises

In this lesson, we delve into promises, a powerful feature introduced in ES6 for handling asynchronous code in JavaScript. Here's an overview of the topics covered:

1. Introduction to Promises:
   - Understanding the motivation behind promises and their importance in modern JavaScript development.
   - Exploring the benefits of using promises, including improved code organization and error handling.

2. Promise Flow:
   - Examining the mechanics of promises using the `fetch` function as an example.
   - Understanding how promises enable chaining and how subsequent methods like `then` are triggered upon promise resolution.

3. Microtask Queue and Task Queue:
   - Understanding the microtask queue's role and its priority over the callback queue.
   - Exploring how the event loop manages the call stack, callback queue, and microtask queue for efficient and non-blocking execution.

4. Debugging and Error Handling:
   - Addressing common issues with promises and emphasizing the importance of understanding their underlying mechanisms for effective debugging and error handling.

5. Promises and Web APIs:
   - Highlighting the crucial role of promises in working with web browser APIs and their asynchronous nature.
   - Clarifying concepts such as passing functions by reference/value and the behavior of arguments within web APIs.

6. Benefits and Challenges:
   - Summarizing the benefits of using promises, including cleaner code and improved error handling.
   - Acknowledging the challenges developers may face due to the complexity of asynchronous JavaScript.

### Example : Fetching Data with Promises

```javascript
function display(data) {
  console.log(data);
}

const fetchData = fetch('https://api.example.com/data');

fetchData
  .then(response => response.json())
  .then(data => display(data))
  .catch(error => console.log(error));

console.log("Me first!");
```

In this example, the `fetch` function is used to make an API call and returns a Promise. The subsequent `.then` method is used to handle the resolved Promise by parsing the response as JSON and passing it to the `display` function. The `.catch` method handles any errors that occur during the Promise chain. While the Promise is being resolved, "Me first!" is logged to the console.

## Coding Exercises

### [Exercises for Async JS & Promises](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)

#### My Solution
```javascript
const task1 = (cb) =>
  setTimeout(() => {
    const message = "Task 1 has executed successfully!";
    cb(message);
  }, 3000);

const task2 = (cb) =>
  setTimeout(() => {
    const message = "Task 2 has executed successfully!";
    cb(message);
  }, 0);

const task3 = (cb) =>
  setTimeout(() => {
    const message = "Task 3 has executed successfully!";
    cb(message);
  }, 1000);

const task4 = (cb) =>
  setTimeout(() => {
    const message = "Task 4 has executed successfully!";
    cb(message);
  }, 2000);

const task5 = (cb) =>
  setTimeout(() => {
    const message = "Task 5 has executed successfully!";
    cb(message);
  }, 4000);

const asyncTasks = [task1, task2, task3, task4, task5];
const executeInSequenceWithCBs = (tasks, callback) => {
  const messages = [];

  tasks.forEach((task) =>
    task((message) => {
      messages.push(message);
      callback(messages);
    })
  );
};
const callback = (messages) => {
  console.log("Messages:", messages);
};

executeInSequenceWithCBs(asyncTasks, callback);

Question 3:

const apis = [
  {
    apiName: "products",
    apiUrl: "https://dummyjson.com/products",
  },
  {
    apiName: "users",
    apiUrl: "https://dummyjson.com/users",
  },
  {
    apiName: "posts",
    apiUrl: "https://dummyjson.com/posts",
  },
  {
    apiName: "comments",
    apiUrl: "https://dummyjson.com/comments",
  },
];
const executeInSequenceWithPromises = (apis) => {
  const promises = apis.map((api) => {
    return fetch(api.apiUrl)
      .then((response) => response.json())
      .then((apiData) => ({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData,
      }));
  });

  return Promise.all(promises);
};

executeInSequenceWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error(error);
  });

```
