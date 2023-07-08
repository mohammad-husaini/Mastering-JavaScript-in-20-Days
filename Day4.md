# Day 4: Event Handlers, Conditionals, Map and Filter

This README file summarizes the JavaScript lessons on event handlers, conditionals, and map/filter methods. We explore how to handle events on the DOM, work with conditional statements, and utilize the map and filter methods for array manipulation.

## Lesson 1: Event Handlers

Event handlers allow us to detect and respond to events on the DOM. Here are the key points covered in this lesson:

- We can use the `.addEventListener` method to attach event listeners to DOM elements.
- Event listeners take in two parameters: the name of the event to listen for, and a handler function to run when the event occurs.
- The event object provides information about the event, such as the target element and event type.
```javascript
// Example 1: Event Handlers
const button = document.querySelector("#myButton");

button.addEventListener("click", () => {
  console.log("Button clicked!");
});
```
## Lesson 2: Conditionals

Conditionals allow us to execute code based on certain conditions. Here are the key points covered in this lesson:

- Conditional statements, such as `if` and `else`, allow us to run different blocks of code based on specific conditions.
- Logical operators like `&&` (and), `||` (or), and `!` (not) can be used to create complex conditional expressions.
- Loops, such as `for` and `while`, allow us to repeat code execution based on a specified condition.
```javascript
// Example 2: Conditionals
const age = 21;
const name = "Mohammad Husaini";

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}

if (name.length > 10) {
  console.log("Your name is long.");
} else {
  console.log("Your name is short.");
}

```
## Lesson 3: Map and Filter

The `map` and `filter` methods provide powerful tools for array manipulation. Here are the key points covered in this lesson:

- The `map` method iterates over an array and calls a function on each item, creating a new array with the results.
- The `filter` method processes an array and returns a new array containing only the items that meet a specified condition.
- The spread operator (`...`) can be used to insert all items from one array into another.
  
```javascript
// Example 3: Map and Filter
const numbers = [1, 2, 3, 4, 5];

const multipliedNumbers = numbers.map((num) => num * 2);
console.log(multipliedNumbers); // Output: [2, 4, 6, 8, 10]

const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
// Example: Using the Spread Operator
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

const combinedArray = [...array1, ...array2];

console.log(combinedArray);
// Output: [1, 2, 3, 4, 5, 6]

```
## Coding Examples

```html
//The Complete Quiz from Day3
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
        answer: "false",
        explanation:
          "because its a string and when we add it to gother is will be 11 ",
      };
      1;
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
      for (let button of optionButtons) {
        button.addEventListener("click", (event) => {
          explanation.textContent = fact.explanation;
          // TODO 7: Within the event handler function,
          // Use a for loop to disable all the option buttons
          for (const button of optionButtons) {
            disable(button);
          }

          // TODO 8: Within the event handler function,
          // Get the guessed value from the clicked button
          // Use a conditional to compare the guess to the fact's answer
          // and add the "correct"/"incorrect" class as appropriate
          console.log(button.value);
          console.log(typeof button.value);
          isCorrect(button.value)
            ? button.classList.add("correct")
            : button.classList.add("incorrect");
        });
      }
    </script>
  </body>
</html>

```
## Lesson 4: Doggos Quiz Game

In this lesson, we introduce a fun project: the Doggos Quiz Game. Here's a summary of what we cover:

- Setup instructions for the Doggos Quiz Game project.
- The project involves creating a "guess the dog breed" quiz.

## Coding Exercises

### [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)

#### My Solution
```javascript
function checkSign(num) {
return num===0?"zero":num>0?"positive":"negative";
}

checkSign(10);
```

### [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)

#### My Solution
```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line


  return strokes===1?names[0]:strokes<=par-2?names[1]:strokes===par-1?names[2]:strokes===par?names[3]:strokes===par+1?names[4]:strokes===par+2?names[5]:"Go Home!";
  // Only change code above this line
}

golfScore(5, 4);
```

### [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)

#### My Solution
```javascript
// Only change code below this line

const ratings = watchList.map((movie) => {
  return {
    title: movie.Title,
    rating: movie.imdbRating,
  };
});


// Only change code above this line

console.log(JSON.stringify(ratings));

```

### [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)

#### My Solution
```javascript
// Only change code below this line
const notFilteredList = watchList.map((movie) => {
  return {
    title: movie.Title,
    rating: movie.imdbRating,
  };
});
const filteredList = notFilteredList
.filter(e=>e.rating > 8)
// Only change code above this line
```
