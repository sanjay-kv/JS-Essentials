# JS-Essentials

This repository provides a comprehensive overview of key JavaScript concepts, including data types, hoisting, closures, and more. The content is designed for developers looking to deepen their understanding of JavaScript.

### Top most asked javascript 
1. What are the different data types in JavaScript?
2. Explain the concept of hoisting in JavaScript.
3. What is the difference between `==` and `===` in JavaScript?
4. What is a closure in JavaScript?
5. What is the difference between `function declaration` and `function expression`?
6. What is the `this` keyword in JavaScript, and how does it work?
7. How do you clone an object in JavaScript?
8. What is the difference between `null` and `undefined`?
9. Explain the concept of prototypal inheritance.
10. What is the difference between `setTimeout()` and `setInterval()`?
11. What is a Promise, and how does it work?
12. What is async/await and how does it simplify working with Promises?
13. What is the event loop in JavaScript?
14. Explain the concept of debouncing and throttling.

## 1. Different Data Types in JavaScript

JavaScript has several data types:
- **Primitive Types**:
  - **Number**: Represents both integer and floating-point numbers.
  - **String**: Represents text.
  - **Boolean**: Represents logical values `true` and `false`.
  - **Null**: Represents the intentional absence of any object value.
  - **Undefined**: Represents a variable that has been declared but not yet assigned a value.
  - **Symbol**: Represents a unique and immutable value.
  - **BigInt**: Represents integers with arbitrary precision.
- **Composite Types**:
  - **Object**: Represents collections of properties.
  - **Array**: A type of object that holds a collection of values in an ordered list.

## 2. Concept of Hoisting in JavaScript

Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that variables and functions can be used before they are declared in the code.

```javascript
console.log(x); // undefined
var x = 5;
```

## 3. Difference Between `==` and `===` in JavaScript

- **`==` (Loose Equality)**: Compares two values for equality, after converting both values to a common type (type coercion).
- **`===` (Strict Equality)**: Compares two values for equality without type conversion, meaning both the value and the type must be the same.

```javascript
console.log(5 == '5');  // true
console.log(5 === '5'); // false
```

## 4. Closure in JavaScript

A closure is a function that retains access to its lexical scope even when the function is executed outside that scope. Closures allow a function to access variables from an outer function even after the outer function has finished executing.

```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

## 5. Difference Between `Function Declaration` and `Function Expression`

- **Function Declaration**: A function that is declared as a standalone statement. It is hoisted, meaning it can be called before it is defined in the code.

```javascript
function greet() {
  console.log('Hello');
}
```

- **Function Expression**: A function assigned to a variable. It is not hoisted, so it cannot be called before the expression is evaluated.

```javascript
const greet = function() {
  console.log('Hello');
};
```

## 6. The `this` Keyword in JavaScript

The `this` keyword refers to the context in which a function is called:
- In a method, `this` refers to the object the method is called on.
- In a regular function, `this` refers to the global object (`window` in browsers) unless in strict mode, where it is `undefined`.
- In an event, `this` refers to the element that received the event.
- In arrow functions, `this` retains the value of the enclosing lexical context.

```javascript
const obj = {
  name: 'Alice',
  greet: function() {
    console.log(this.name);
  }
};

obj.greet(); // 'Alice'
```

## 7. Cloning an Object in JavaScript

There are several ways to clone an object in JavaScript:
- **Shallow Copy**:

```javascript
const original = { a: 1, b: 2 };
const copy = Object.assign({}, original);
```

```javascript
const copy = { ...original };
```

- **Deep Copy** (for nested objects):

```javascript
const deepCopy = JSON.parse(JSON.stringify(original));
```

- **Using `structuredClone`** (for deep copy):

```javascript
const deepCopy = structuredClone(original);
```

## 8. Difference Between `null` and `undefined`

- **`null`**: Represents the intentional absence of any object value. It is explicitly assigned by a developer.
- **`undefined`**: Represents a variable that has been declared but not yet assigned a value. It can also be returned when accessing a non-existing property of an object or calling a function that doesn't return a value.

## 9. Concept of Prototypal Inheritance

JavaScript uses prototypal inheritance, where objects inherit properties and methods from other objects. Every object has a prototype, which is another object from which it inherits properties.

```javascript
const person = {
  greet() {
    console.log('Hello');
  }
};

const alice = Object.create(person);
alice.greet(); // 'Hello'
```

## 10. Difference Between `setTimeout()` and `setInterval()`

- **`setTimeout()`**: Executes a function once after a specified delay.

```javascript
setTimeout(() => {
  console.log('Executed after 2 seconds');
}, 2000);
```

- **`setInterval()`**: Repeatedly executes a function with a fixed time delay between each call.

```javascript
setInterval(() => {
  console.log('Executed every 2 seconds');
}, 2000);
```

## 11. Promises in JavaScript

A Promise is an object representing the eventual completion or failure of an asynchronous operation. It allows you to attach handlers for the eventual result or error.

```javascript
let promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success!"), 2000);
});

promise.then(result => console.log(result)); // "Success!" after 2 seconds
```

## 12. Async/Await in JavaScript

`async/await` is syntactic sugar built on Promises, allowing you to write asynchronous code that looks synchronous.

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

## 13. The Event Loop in JavaScript

The event loop is a mechanism in JavaScript that handles asynchronous operations. It allows non-blocking code execution by offloading tasks to the event loop and continuing with other operations.

## 14. Debouncing and Throttling

- **Debouncing**: Ensures that a function is only called once after a specified delay, regardless of how many times the event is triggered.

```javascript
function debounce(func, delay) {
  let timeout;
  return function() {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, arguments), delay);
  };
}
```

- **Throttling**: Ensures that a function is called at most once in a specified interval, preventing it from being called too frequently.

```javascript
function throttle(func, interval) {
  let lastCall = 0;
  return function() {
    const now = Date.now();
    if (now - lastCall >= interval) {
      lastCall = now;
      func.apply(this, arguments);
    }
  };
}
```



