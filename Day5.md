# Day 5: Data Fetching, Promises, Destructuring, Async, and Modules

This README file summarizes the JavaScript lessons on data fetching, promises, destructuring, async functions, and modules.

## Lesson 1: Data Fetching & Promises

In this lesson, we explore fetching data from an API endpoint using the `fetch` function and working with promises. Here are the key points covered in this lesson:

- Using the `fetch` function to load data from an API endpoint.
- Understanding the states of a promise: pending, fulfilled, and rejected.
- Using the `await` operator to wait for a promise and obtain its resulting value.

**Example: Fetching Data**

```javascript
async function fetchData(url) {
  const response = await fetch(url);
  const data = await response.json();
  return data;
}

const apiUrl = "https://api.example.com/data";
const result = await fetchData(apiUrl);
console.log(result);
```

## Lesson 2: Destructuring Data

Destructuring allows us to declare multiple variables at once by extracting values from objects or arrays. Here are the key points covered in this lesson:

- Destructuring objects to retrieve values from properties.
- Destructuring arrays using square brackets.
- Applying destructuring in various scenarios to simplify code.

**Example: Destructuring Objects**

```javascript
const person = {
  name: "Mohammad Husaini",
  age: 21,
  city: "Hebron",
};

const { name, age } = person;
console.log(name); // Output: "Mohammad Husaini"
console.log(age); // Output: 21
```

## Lesson 3: Async Functions

Async functions provide a cleaner syntax for writing asynchronous code. Here are the key points covered in this lesson:

- Combining async fetching and parsing into a single function.
- Using the `await` keyword to retrieve the contents of a returned promise.
- Handling errors and exceptions in async functions.

**Example: Async Function**

```javascript
async function fetchData(url) {
  try {
    const response = await fetch(url);
    const data = await response.json();
    return data;
  } catch (error) {
    console.error(error);
    throw new Error("An error occurred while fetching data.");
  }
}

const apiUrl = "https://api.example.com/data";
try {
  const result = await fetchData(apiUrl);
  console.log(result);
} catch (error) {
  console.error(error);
}
```

## Lesson 4: Modules

Modules allow us to split large codebases into smaller files for better organization and reusability. Here are the key points covered in this lesson:

- Understanding the differences between JavaScript and module JavaScript.
- Importing and exporting modules using the `import` and `export` keywords.
- Debugging and error handling techniques.

**Example: Module Imports and Exports**

```javascript
// Module 1: math.js
export function add(a, b) {
  return a + b;
}

// Module 2: utils.js
export function capitalize(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

// Main file: main.js
import { add } from "./math.js";
import { capitalize } from "./utils.js";

console.log(add(2, 3)); // Output: 5
console.log(capitalize("hello")); // Output: "Hello"
```

## Coding Example

```html

<!DOCTYPE html>
<!-- saved from url=(0068)https://anjana.dev/javascript-first-steps/3-doggofetch-finished.html -->
<html lang="en-US"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Doggo Fetch</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }
        header {
            width: 70%;
            margin: 1em auto;
        }
        main {
            max-width: 70%;
            margin: 0px auto;
            display:flex; 
            flex-direction: column;
        }
        img {
            max-width: 100%;
        }
        #image-frame {
            font-size: x-large;
            text-align: center;
            margin: 1rem auto;
        }
        #explanation, #score {
            padding: 1rem;
            text-align: center;
        }
        #options {
            max-width: 100%;
            display: flex;
            flex-direction: column;
        }
        button {
            padding: 0.5rem;
            font-size: medium;
            border-radius: 5px;
        }
        .correct {
            background-color: lightgreen;
        }
        .incorrect {
            background-color: lightpink;
        }
        .hidden {
            display: none;
        }
    </style>
  </head>
  <body>
    <header>
    <h1>Guess the Doggo</h1>
    <p>What breed is the dog in this image?</p>

    </header>

    <main>
    <div id="image-frame"><img src="./Doggo Fetch22_files/n02108089_2608.jpg"></div>
    <div id="options">
    <button name="dalmatian" value="dalmatian">dalmatian</button><button name="border terrier" value="border terrier">border terrier</button><button name=" boxer" value=" boxer"> boxer</button></div>

    </main>

  


  <script type="module">

    const RANDOM_IMG_ENDPOINT = "https://dog.ceo/api/breeds/image/random";

    const BREEDS = ["affenpinscher", "african", "airedale", "akita", "appenzeller", "shepherd australian", "basenji", "beagle", "bluetick", "borzoi", "bouvier", "boxer", "brabancon", "briard", "norwegian buhund", "boston bulldog", "english bulldog", "french bulldog", "staffordshire bullterrier", "australian cattledog", "chihuahua", "chow", "clumber", "cockapoo", "border collie", "coonhound", "cardigan corgi", "cotondetulear", "dachshund", "dalmatian", "great dane", "scottish deerhound", "dhole", "dingo", "doberman", "norwegian elkhound", "entlebucher", "eskimo", "lapphund finnish", "bichon frise", "germanshepherd", "italian greyhound", "groenendael", "havanese", "afghan hound", "basset hound", "blood hound", "english hound", "ibizan hound", "plott hound", "walker hound", "husky", "keeshond", "kelpie", "komondor", "kuvasz", "labradoodle", "labrador", "leonberg", "lhasa", "malamute", "malinois", "maltese", "bull mastiff", "english mastiff", "tibetan mastiff", "mexicanhairless", "mix", "bernese mountain", "swiss mountain", "newfoundland", "otterhound", "caucasian ovcharka", "papillon", "pekinese", "pembroke", "miniature pinscher", "pitbull", "german pointer", "germanlonghair pointer", "pomeranian", "medium poodle", "miniature poodle", "standard poodle", "toy poodle", "pug", "puggle", "pyrenees", "redbone", "chesapeake retriever", "curly retriever", "flatcoated retriever", "golden retriever", "rhodesian ridgeback", "rottweiler", "saluki", "samoyed", "schipperke", "giant schnauzer", "miniature schnauzer", "english setter", "gordon setter", "irish setter", "sharpei", "english sheepdog", "shetland sheepdog", "shiba", "shihtzu", "blenheim spaniel", "brittany spaniel", "cocker spaniel", "irish spaniel", "japanese spaniel", "sussex spaniel", "welsh spaniel", "english springer", "stbernard", "american terrier", "australian terrier", "bedlington terrier", "border terrier", "cairn terrier", "dandie terrier", "fox terrier", "irish terrier", "kerryblue terrier", "lakeland terrier", "norfolk terrier", "norwich terrier", "patterdale terrier", "russell terrier", "scottish terrier", "sealyham terrier", "silky terrier", "tibetan terrier", "toy terrier", "welsh terrier", "westhighland terrier", "wheaten terrier", "yorkshire terrier", "tervuren", "vizsla", "spanish waterdog", "weimaraner", "whippet", "irish wolfhound"];

    
    // Utility function to get a randomly selected item from an array
    function getRandomElement(array) {
        const i = Math.floor(Math.random() * array.length);
        return array[i];
    }

    // Utility function to shuffle the order of items in an array in-place
    function shuffleArray(array) {
        return array.sort((a,b) => Math.random() - 0.5);
    }



    // TODO 1
    // Given an array of possible answers, a correct answer value, and a number of choices to get,
    // return a list of that many choices, including the correct answer and others from the array
    function getMultipleChoices(n, correctAnswer, array) {
        // Use a while loop and the getRandomElement() function
        // Make sure there are no duplicates in the array
        const choices = [correctAnswer];
        while (choices.length < n) {
            let candidate = getRandomElement(array);
            if (choices.indexOf(candidate) < 0) { // check if this is already in the array
                choices.push(candidate); // if not, add it
            }
        }
        return shuffleArray(choices);
    }

    
    // TODO 2
    // Given a URL such as "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
    // return the breed name string as formatted in the breed list, e.g. "standard poodle"
    function getBreedFromURL(url) {
        // The string method .split(char) may come in handy
        // Try to use destructuring as much as you can
        const [,path] = url.split("/breeds/");
        const [breedID] = path.split("/");
        const [breed, subtype] = breedID.split("-");
        return [subtype, breed].join(" ");
    }



    // TODO 3
    // Given a URL, fetch the resource at that URL, 
    // then parse the response as a JSON object,
    // finally return the "message" property of its body
    async function fetchMessage(url) {
        const response = await fetch(url);  // Fetch the resource at the given URL
        const {message} = await response.json(); // Parse the response as JSON & remember its 'message' value
        return message; // Return the message
    }


    // Function to add the multiple-choice buttons to the page
    function renderButtons(choicesArray, correctAnswer) {

        // Event handler function to compare the clicked button's value to correctAnswer
        // and add "correct"/"incorrect" classes to the buttons as appropriate
        function buttonHandler(e) {
            if (e.target.value === correctAnswer) {
                e.target.classList.add("correct");
            } else {
                e.target.classList.add("incorrect");
                document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
            }
        }

        const options = document.getElementById("options"); // Container for the multiple-choice buttons

        // TODO 4
        // For each of the choices in choicesArray,
        // Create a button element whose name, value, and textContent properties are the value of that choice,
        // attach a "click" event listener with the buttonHandler function,
        // and append the button as a child of the options element
        choicesArray.map(choice => {
            let button = document.createElement("button");
            button.value = button.name = button.textContent = choice;
            button.addEventListener("click", buttonHandler);
            options.appendChild(button);
        })
    }


    // Function to add the quiz content to the page
    function renderQuiz(imgUrl, correctAnswer, choices) {
        const image = document.createElement("img");
        image.setAttribute("src", imgUrl);
        const frame = document.getElementById("image-frame");

        image.addEventListener("load", () => {
            // Wait until the image has finished loading before trying to add elements to the page
            frame.replaceChildren(image);
            renderButtons(choices, correctAnswer);
        })
        
    }

    // Function to load the data needed to display the quiz
    async function loadQuizData() {
        document.getElementById("image-frame").textContent = "Fetching doggo...";
        
        const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
        const correctBreed = getBreedFromURL(doggoImgUrl);
        const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

        return [doggoImgUrl, correctBreed, breedChoices];
    }

    // TODO 5
    // Asynchronously call the loadQuizData() function,     
    // Then call renderQuiz() with the returned imageUrl, correctAnswer, and choices 
    const [imageUrl, correctAnswer, choices] = await loadQuizData();
    renderQuiz(imageUrl, correctAnswer, choices);
    


  </script>

</body></html>
```
## Coding Exercises

### [Build a Rick & Morty characters list](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)

#### My Solution
#### Javascript
```javascript
const ul = document.getElementById("characterList");
const fetchApi = async () => {
  try {
    const response = await fetch("https://rickandmortyapi.com/api/character");
    const resultsJson = await response.json();
    const results = await resultsJson.results;
    return results;
  } catch (error) {
    console.log("Failed to fetch");
    console.log(error);
  }
};
const filterResult = async (results) => {
  const res = await results;
  const filter = res.filter((e) => e.status === "Alive");
  console.log(filter);
  return filter;
};

const renderResult = async () => {
  const data = await filterResult(fetchApi());
  data.slice(0, 50).forEach((element) => {
    const li = document.createElement("li");
    const div = document.createElement("div");
    const h1 = document.createElement("h1");
    const img = document.createElement("img");
    const p = document.createElement("p");
    h1.textContent = element.name;
    img.src = element.image;
    p.innerHTML = `<strong>Location:</strong> ${element.location.name}<br>
    <strong>Species:</strong> ${element.species}<br>
    <strong>Gender:</strong> ${element.gender}`;
    div.appendChild(h1);
    div.appendChild(img);
    div.appendChild(p);
    li.appendChild(div);
    ul.appendChild(li);
  });
};
renderResult();

```
#### HTML
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Alive Character List</title>
    <link rel="stylesheet" href="./styles.css" />
    <link
      href="https://fonts.googleapis.com/css2?family=Roboto&family=Get+Schwifty&display=swap"
      rel="stylesheet"
    />
  </head>
  <body>
    <h1>Alive Character List</h1>
    <ul id="characterList"></ul>

    <script src="./script.js"></script>
  </body>
</html>

```
#### CSS
```css
body {
  font-family: "Roboto", sans-serif;
  background-color: #222831;
  color: #ffffff;
  margin: 0;
  padding: 20px;
}

h1 {
  color: #00adb5;
  text-align: center;
  margin-bottom: 30px;
  font-family: "Get Schwifty", cursive;
  font-size: 48px;
  animation: fadeIn 1s ease-in-out;
  text-transform: uppercase;
  letter-spacing: 4px;
  text-shadow: 2px 2px 4px rgba(0, 173, 181, 0.3);
}

ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

li {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 10px;
  border: 2px solid #00adb5;
  padding: 20px;
  width: 400px;
  background-color: #393e46;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 173, 181, 0.2);
  transition: transform 0.3s ease-in-out;
  position: relative;
}

li::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #00adb5;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
  z-index: -1;
}

li:hover {
  transform: translateY(-10px);
}

li:hover::before {
  opacity: 0.2;
}

div {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 30px;
}

img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
  margin-bottom: 20px;
  animation: rotate 2s infinite linear;
  transition: transform 0.3s ease-in-out;
  border: 4px solid #00adb5;
  box-shadow: 0 0 10px rgba(0, 173, 181, 0.5);
}

img:hover {
  transform: scale(1.2);
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

p {
  font-size: 18px;
  color: #ffffff;
  text-align: center;
}

```
## Live 
![ezgif-1-d9215cb02c](https://github.com/mohammad-husaini/Mastering-JavaScript-in-20-Days/assets/125281502/a9c85d67-d26b-4da2-af8f-1cdab7f07c3d)



