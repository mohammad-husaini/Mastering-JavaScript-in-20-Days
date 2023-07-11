# Day 9: Classes & Prototypes

This README file summarizes the JavaScript lesson on Classes & Prototypes covered in Day 9 of the course.

## Lesson: Classes & Prototypes

In this lesson, we delve into the important concepts of classes and prototypes in JavaScript. Here are the key points covered in this lesson:

1. Introduction to classes and their significance: Classes are essential for structuring code in a way that is easy to reason about, maintain, and extend. Object-oriented programming is introduced as a powerful approach to achieving these goals.

2. Storing data and functionality together: The concept of storing data and functions together in one place is introduced. Dot notation is explained as a means to assign and access elements in an object, including functions.

3. Object creation with Object.create(): The built-in function `Object.create()` is introduced as a way to create objects with more control. The concept of a generalized function to produce objects is presented.

4. Understanding the prototype chain: The `__proto__` property is introduced as a way to access functions set when using `Object.create()` to instantiate an object. The prototype chain is explained as the mechanism for linking objects to their prototypes.

5. Factory functions and prototypal links: Factory functions that utilize `Object.create()` with a function argument to create objects with prototypal links to the desired functionality are demonstrated.

6. Clarifying property storage with hasOwnProperty(): The `hasOwnProperty` method is introduced to determine whether an object has a specific property, clarifying where properties are stored.

7. Exploring the behavior of `this`: The behavior of `this` in nested functions is explored, and the `call` and `apply` methods are introduced as a means to control the assignment of `this`. The impact of arrow functions on `this` is also discussed.

8. Introduction to the `new` keyword and object instantiation: The `new` keyword is introduced as a way to automate the process of object instantiation. The inner workings of the `new` keyword are demonstrated, highlighting its use in accessing the prototype object.

9. Syntactic sugar with classes: The `class` keyword is introduced as a syntactic sugar for prototypal inheritance. The benefits and potential issues of using the `class` keyword are discussed.

The lesson on Classes & Prototypes provides a comprehensive understanding of object-oriented programming in JavaScript, enabling developers to structure their code effectively and leverage the power of classes and prototypes in their applications.

## Code Examples

Here are some code examples covered in the lesson:

1. Storing data and functionality in an object:
```javascript
const user1 = {
  name: "Will",
  score: 3,
  increment: function() {
    user1.score++;
  }
};

user1.increment(); // user1.score -> 4
```

2. Creating objects using a function:
```javascript
function userCreator(name, score) {
  const newUser = {};
  newUser.name = name;
  newUser.score = score;
  newUser.increment = function() {
    newUser.score++;
  };
  return newUser;
}

const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);

user1.increment();
```

3. Creating objects using the prototype chain:
```javascript
function userCreator(name, score) {
  const newUser = Object.create(userFunctionStore);
  newUser.name = name;
  newUser.score = score;
  return newUser;
}

const userFunctionStore = {
  increment: function() {
    this.score++;
  },
  login: function() {
    console.log("Logged in");
  }
};

const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);

user1.increment();
```

4. Creating objects using the `new` keyword:
```javascript
function UserCreator(name, score) {
  this.name = name;
  this.score = score;
}

UserCreator.prototype.increment = function() {
  this.score++;
};

const user1 = new UserCreator("Will", 3);
user1.increment();
```

5. Using classes for object creation:
```javascript
class UserCreator {
  constructor(name, score) {
    this.name = name;
    this.score = score;
  }
  
  increment() {
    this.score++;
  }
  
  login() {
    console.log("Login");
  }
}

const user1 = new UserCreator("Will", 3);
user1.increment();
```

## Coding Exercises

### [Object Oriented Programming in FreeCodeCamp.](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day4-tasks/tasks.md)



