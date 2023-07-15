# Day 9: Classes & Prototypes

This README file summarizes the JavaScript lesson on Classes & Prototypes covered in Day 9 of the course.

## Lesson : Classes & Prototypes

In this lesson, we will delve into the important concepts of classes and prototypes in JavaScript. We'll explore how they are used to create and organize objects and methods. Here's a breakdown of the topics covered:

1. Introduction to Object-Oriented Programming:
   - Understanding the significance of object-oriented programming (OOP) as a popular paradigm for structuring complex code.
   - Exploring the benefits of OOP, including code organization, ease of adding new functionality, and code efficiency.
   
   Example:
   ```javascript
   class Animal {
     constructor(name) {
       this.name = name;
     }
     
     speak() {
       console.log(`${this.name} makes a sound.`);
     }
   }
   
   const dog = new Animal('Dog');
   dog.speak(); // Output: Dog makes a sound.
   ```

2. Storing Data and Functionality Together:
   - Making the case for storing data and functionality together in one place for better organization and maintainability.
   - Introducing dot notation as a way to assign and access properties, including functions, within an object.
   
   Example:
   ```javascript
   const person = {
     name: 'John',
     age: 30,
     greet: function() {
       console.log(`Hello, my name is ${this.name}.`);
     }
   };
   
   person.greet(); // Output: Hello, my name is John.
   ```

3. Creating Objects with Object.create():
   - Introducing the `Object.create()` method as a way to create objects that provide more control and customization.
   - Understanding the concept of a generalized function that produces objects.
   
   Example:
   ```javascript
   const personPrototype = {
     greet: function() {
       console.log(`Hello, my name is ${this.name}.`);
     }
   };
   
   const person = Object.create(personPrototype);
   person.name = 'John';
   person.greet(); // Output: Hello, my name is John.
   ```

4. The Prototype Chain and __proto__:
   - Exploring the prototype chain and the `__proto__` property as a mechanism to access functions defined when using `Object.create()`.
   
   Example:
   ```javascript
   const parent = {
     greet: function() {
       console.log(`Hello, I'm the parent.`);
     }
   };
   
   const child = Object.create(parent);
   child.greet(); // Output: Hello, I'm the parent.
   ```

5. Factory Functions and Prototypal Inheritance:
   - Demonstrating how factory functions can utilize `Object.create()` to create objects with a prototypal link to shared functionality.
   - Understanding how objects created with factory functions share methods but have their own data.
   
   Example:
   ```javascript
   const animalFactory = (name) => {
     const animal = Object.create(animalFactory.prototype);
     animal.name = name;
     return animal;
   };
   
   animalFactory.prototype.speak = function() {
     console.log(`${this.name} makes a sound.`);
   };
   
   const dog = animalFactory('Dog');
   dog.speak(); // Output: Dog makes a sound.
   ```

6. The "this" Keyword and Execution Context:
   - Addressing the behavior of the "this" keyword when used within nested functions or different contexts.
   - Introducing the `call()` and `apply()` methods as ways to explicitly control the value of "this".
   
   Example:
   ```javascript
   const person = {
     name: 'John',
     greet: function() {
       console.log(`Hello, my name is ${this.name}.`);
     }
   };
   
   const anotherPerson = {
     name: 'Jane'
   };
   
   person.greet.call(anotherPerson); // Output: Hello, my name is Jane.
   ```

7. Arrow Functions and "this" Binding:
   - Understanding how arrow functions override the normal "this" binding rules due to their lexical scoping nature.
   - Discussing the implications of using arrow functions as methods and their interaction with the "this" keyword.
   
   Example:
   ```javascript
   const person = {
     name: 'John',
     greet: () => {
       console.log(`Hello, my name is ${this.name}.`);
     }
   };
   
   person.greet(); // Output: Hello, my name is undefined.
   ```

8. The "new" Keyword and Constructor Functions:
   - Introducing the "new" keyword and its role in automating object creation and method assignment.
   - Understanding the process behind the scenes when using the "new" keyword to instantiate objects.
   
   Example:
   ```javascript
   function Person(name) {
     this.name = name;
   }
   
   Person.prototype.greet = function() {
     console.log(`Hello, my name is ${this.name}.`);
   };
   
   const john = new Person('John');
   john.greet(); // Output: Hello, my name is John.
   ```

9. The Syntactic Sugar of Classes:
   - Exploring the syntactic sugar of the "class" keyword, which simplifies the creation of constructor functions and method assignments.
   - Understanding that classes are just a more readable way of working with prototypes.
   
   Example:
   ```javascript
   class Person {
     constructor(name) {
       this.name = name;
     }
     
     greet() {
       console.log(`Hello, my name is ${this.name}.`);
     }
   }
   
   const john = new Person('John');
   john.greet(); // Output: Hello, my name is John.
   ```



## Coding Exercises

### [Object Oriented Programming in FreeCodeCamp.](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day4-tasks/tasks.md)

### [ My Solution](https://www.freecodecamp.org/Mohammad_Husaini)


