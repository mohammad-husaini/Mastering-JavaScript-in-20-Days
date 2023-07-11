# Day 8: Asynchronous JavaScript and Promises

This README file summarizes the JavaScript lessons on Asynchronous JavaScript and Promises covered in Day 8 of the course.

## Lesson 1: Asynchronous JavaScript

In this lesson, we delve into the concept of Asynchronous JavaScript, which enables dynamic web applications by handling time-consuming tasks without blocking execution. Here are the key points covered in this lesson:

1. Understanding JavaScript's execution model: JavaScript is single-threaded and executes code synchronously, following the order in which it appears.

2. Challenges with synchronous code and accessing external resources: Performing tasks that require waiting for external resources, such as API calls, can cause the code to block and hinder further execution.

3. Introduction to web browser APIs: Web browsers provide additional features and APIs, such as `setTimeout`, which allow JavaScript to handle asynchronous operations without blocking.

4. Event loop and task queues: The event loop manages the execution of code and handles the prioritization of tasks in different queues, such as the callback queue and microtask queue.

Lesson 1 provides an overview of the basics of handling asynchronous JavaScript and lays the foundation for understanding more complex asynchronous operations.

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

In this lesson, we explore Promises, a powerful feature introduced in ES6 for managing asynchronous operations in a more structured and efficient way. Here are the key points covered in this lesson:

1. Introduction to Promises: Promises provide a solution to the challenges of managing asynchronous code, offering a more organized and readable approach.

2. Two-pronged "facade" functions: JavaScript provides "facade" functions, such as `fetch`, that initiate background web browser work and return Promises as placeholders for the eventual completion or failure of the asynchronous task.

3. Chaining promises with the `then` method: Promises can be chained together using the `then` method, allowing for sequential execution of dependent asynchronous operations.

4. Event loop and task execution: The event loop plays a crucial role in managing the execution of Promises and ensuring that callback functions are called when promises are fulfilled.

Lesson 2 provides a deeper understanding of Promises and their usage in handling asynchronous operations. It highlights the benefits of Promises, such as cleaner code and improved error handling.

The lessons on Asynchronous JavaScript and Promises equip developers with essential knowledge and techniques to handle asynchronous operations effectively, making their web applications more responsive and efficient.
Certainly! Here are some examples to illustrate the concepts covered in the lessons:

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


```

