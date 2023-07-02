# Day 3: Quiz Project and Functions 
This README file summarizes the JavaScript lessons on the Quiz Project and Functions. In this section, we will explore how to build a quiz project using JavaScript and learn about functions in JavaScript.

## Quiz Project

In this session, we focused on the Quiz Project. Here's a summary of what we covered:

- **JavaScript Pop Quiz Overview**: We started the day with a brief overview of the JavaScript pop quiz, which tested our understanding of the material covered so far. We discussed the contents of the quiz project, including script tags and code comments.

- **DOM Exercise**: We were given a DOM exercise to review our JavaScript skills. The task involved declaring variables such as `statement`, `optionButtons`, and `explanation`, and creating a `facts` object. We learned how to use the `statement` element to display a fact from the object.

- **Declaring and Assigning Variables**: In the second part of the exercise, we declared and assigned a variable called `fact`. This variable was a constant object containing properties such as `fact`, `answer`, and `explanation`. We learned how to set the text of the `statement` element to the fact statement.

## Function

In this session, we dived into functions within the Quiz Project. Here's a summary of what we covered:

- **Declaring and Calling Functions**: We explored the basics of declaring and calling functions. We discussed the difference between function parameters and arguments, and how functions handle incorrect arguments.

- **Return Statements**: We learned how to specify the output value of a function using the return statement. We also discussed scenarios where there is no return statement. We clarified any confusion regarding the similarity between a return statement and `console.log`.

- **Arrow Functions**: Arrow functions are a concise way to write functions in JavaScript. They provide a shorter syntax compared to traditional function expressions. Here are some key points about arrow functions:

  - Arrow functions are defined using the arrow (`=>`) syntax.
  - Arrow functions have a shorter syntax compared to regular function expressions, making code more concise and readable.
  - If the arrow function has only one parameter, the parentheses around the parameter can be omitted.
  - When the function body consists of a single expression, the curly braces and the `return` keyword can be omitted.
  
  Example Usage of Arrow Functions:
  
  ```javascript
  // Traditional function expression
  function add(a, b) {
    return a + b;
  };
  
  // Arrow function
  const add = (a, b) => a + b;
  
  // Arrow function with a single parameter and implicit return
  const square = x => x * x;
  
  // Arrow function with multiple statements
  const greet = name => {
    console.log(`Hello!`);
    console.log(`Mohammad`);
    return "Hello";
  };
  ```
## Scope and Differences Between `let` and `var`

JavaScript has the concept of variable scope, which determines the accessibility and lifetime of variables. There are two main types of scope in JavaScript: global scope and local scope. 

- **Global Scope**: Variables declared outside any function are considered to be in the global scope. They can be accessed from anywhere in the code, including within functions.

- **Local Scope**: Variables declared within a function are considered to be in the function scope. They are only accessible within that function and any nested functions.

In ES6, the `let` keyword was introduced as an alternative to `var` for declaring variables. Here are some key differences between `let` and `var`:

- **Block Scope**: Variables declared with `let` have block scope, which means they are only accessible within the block of code where they are defined (i.e., within curly braces `{}`). On the other hand, variables declared with `var` have local scope or global scope.

- **Reassignment and Redeclaration**: Variables declared with `let` can be reassigned to a new value, but they cannot be redeclared within the same block scope. In contrast, variables declared with `var` can be both reassigned and redeclared within the same scope.

Here's an example that demonstrates the differences between `let` and `var`:

```javascript
function example() {
  if (true) {
    let x = 10; // block scope variable
    var y = 20; // local scope variable
    console.log(x); // Output: 10
    console.log(y); // Output: 20
  }
  console.log(x); // Error: x is not defined
  console.log(y); // Output: 20
}

example();
```

## Coding Example

```html
<!DOCTYPE html>
<!-- saved from url=(0063)https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html -->
<html lang="en-US">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />

    <title>Quiz.js</title>
    <style>
      body {
        margin: 1rem auto;
        padding: 3rem;
        font-family: sans-serif;
      }
      header {
        width: 50%;
        margin: 1em auto;
      }
      main {
        min-width: 25rem;
        max-width: 50%;
        margin: 0px auto;
        display: flex;
        flex-direction: column;
      }
      #statement {
        border: 1px solid black;
        border-radius: 0.5rem;
        box-shadow: 5px 5px 5px gray;
        padding: 1rem;
        font-size: x-large;
        text-align: center;
        margin: 1rem 0px;
        min-height: 2em;
      }
      #explanation {
        padding: 1rem;
        text-align: center;
      }
      #options {
        width: 100%;
        display: flex;
        flex-direction: column;
      }
      button {
        padding: 0.5rem;
        font-size: medium;
        border-radius: 5px;
      }
      button:hover {
        background-color: bisque;
      }
      .correct {
        background-color: lightgreen;
      }
      .incorrect {
        background-color: lightpink;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Quiz.js</h1>
      <p>Do you know JS? Find out!</p>
    </header>

    <main>
      <div id="statement"></div>

      <div id="options">
        <button name="true" value="true">true</button>
        <button name="false" value="false">false</button>
      </div>

      <div id="explanation"></div>
    </main>

    <script type="text/javascript">
      // TODO 1: Declare & assign variables pointing to the corresponding element(s)
      // statement should be the "statement" div
      const statement = document.getElementById("statement");
      // optionButtons should be all the elements within the "options" div
      const optionButtons = document.querySelectorAll("#options button");
      // explanation should be the "explanation" div
      const explanation = document.getElementById("explanation");
      // TODO 2: Declare & assign a variable called fact
      // Its value should be an object with a statement, true/false answer, and explanation
      const fact = {
        statment: "'1' + '1' === '2'",
        answer: false,
        explanation:
          "because its a string and when we add it to gother is will be 11 ",
      };
      // TODO 3: Set the text of the statement element to the fact's statement
      statement.textContent = fact.statment;
      // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
      // disable(button) should set the button element's attribute "disabled" to the value ""
      const disable = (button) => button.setAttribute("disabled", "");
      // enable(button) should remove the attribute "disabled" from the button element
      const enable = (button) => button.removeAttribute("disabled");
      // TODO 5: Declare an isCorrect function that compares a guess to the right answer
      // isCorrect(guess) should return true if the guess matches the fact's answer
      const isCorrect = (guess) => guess === fact.answer;
      // TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
      // TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element

      // TODO 7: Within the event handler function,
      // Use a for loop to disable all the option buttons

      // TODO 8: Within the event handler function,
      // Get the guessed value from the clicked button
      // Use a conditional to compare the guess to the fact's answer
      // and add the "correct"/"incorrect" class as appropriate
    </script>
  </body>
</html>
```
## Coding Exercises

### [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)

#### My Solution
```javascript

```
### [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

#### My Solution
```javascript

```
### [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)

#### My Solution
```javascript

```
### [Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)

#### My Solution
```javascript

```
### [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)

#### My Solution
```javascript

```
