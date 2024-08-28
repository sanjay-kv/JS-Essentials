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
 
<details><summary>For more details: Click Here 👇</summary>

### JavaScript Data Types

JavaScript has a variety of data types that are categorized into **Primitive Types** and **Composite Types** (also known as Reference Types).

#### **Primitive Types**

1. **Number**
   - Represents both integers and floating-point numbers (decimals).
   - **Example**:
     ```javascript
     let integer = 42;          // Integer
     let floatingPoint = 3.14;  // Floating-point number
     let negative = -7;         // Negative number
     let largeNumber = 1.23e5;  // Exponential notation
     ```
   - **Special Numbers**:
     - `NaN` (Not-a-Number): Represents a computational error.
       ```javascript
       let result = "text" / 2;  // NaN because "text" is not a number
       ```
     - `Infinity` and `-Infinity`: Represent positive and negative infinity.
       ```javascript
       let infinite = 1 / 0;     // Infinity
       let negInfinite = -1 / 0; // -Infinity
       ```

2. **String**
   - Represents a sequence of characters (text).
   - Can be created using single quotes (`'`), double quotes (`"`), or backticks (`` ` ``) for template literals.
   - **Example**:
     ```javascript
     let singleQuoteStr = 'Hello, World!';
     let doubleQuoteStr = "JavaScript is fun!";
     let templateLiteral = `This is a ${singleQuoteStr}`;
     ```

3. **Boolean**
   - Represents logical values: `true` or `false`.
   - Often used in conditional statements.
   - **Example**:
     ```javascript
     let isJavaScriptFun = true;
     let isPythonBetter = false;
     let comparison = 5 > 3;  // true
     ```

4. **Null**
   - Represents the intentional absence of any object value. It is often used to indicate that a variable should have no value.
   - **Example**:
     ```javascript
     let emptyValue = null;
     console.log(emptyValue); // null
     ```

5. **Undefined**
   - Represents a variable that has been declared but not yet assigned a value.
   - If a function does not return a value, it returns `undefined` by default.
   - **Example**:
     ```javascript
     let notAssigned;
     console.log(notAssigned); // undefined

     function doNothing() {}
     console.log(doNothing()); // undefined
     ```

6. **Symbol**
   - Represents a unique and immutable value. It is often used as a key in objects to avoid name collisions.
   - Each `Symbol` is unique, even if it has the same description.
   - **Example**:
     ```javascript
     let symbol1 = Symbol('id');
     let symbol2 = Symbol('id');

     console.log(symbol1 === symbol2); // false
     ```

7. **BigInt**
   - Represents integers with arbitrary precision, allowing you to work with numbers larger than `Number.MAX_SAFE_INTEGER`.
   - Created by appending `n` to the end of an integer.
   - **Example**:
     ```javascript
     let largeNumber = 9007199254740991n;  // BigInt
     let anotherBigInt = BigInt(12345678901234567890);
     ```

#### **Composite Types**

1. **Object**
   - Represents collections of properties. An object is a collection of key-value pairs, where the key is a string (or `Symbol`) and the value can be any data type.
   - **Example**:
     ```javascript
     let person = {
       name: 'John Doe',
       age: 30,
       isEmployed: true,
       greet: function() {
         console.log('Hello, my name is ' + this.name);
       }
     };

     console.log(person.name);  // 'John Doe'
     person.greet();            // 'Hello, my name is John Doe'
     ```

   - **Specialized Objects**:
     - **Date**: Represents date and time.
       ```javascript
       let now = new Date();
       console.log(now);  // Current date and time
       ```
     - **Function**: Functions in JavaScript are first-class objects, meaning they can be stored in variables, passed as arguments, and returned from other functions.
       ```javascript
       let sayHello = function(name) {
         return `Hello, ${name}!`;
       };

       console.log(sayHello('Alice')); // 'Hello, Alice!'
       ```

2. **Array**
   - A type of object that holds a collection of values in an ordered list. Each value (element) in an array has an index, starting from 0.
   - Arrays can contain elements of different types, including other arrays (multidimensional arrays).
   - **Example**:
     ```javascript
     let numbers = [1, 2, 3, 4, 5];
     let mixedArray = [1, 'text', true, null, { key: 'value' }];

     console.log(numbers[0]);  // 1
     console.log(mixedArray[4]); // { key: 'value' }
     ```

   - **Common Array Methods**:
     - `push()`: Adds an element to the end of the array.
     - `pop()`: Removes the last element of the array.
     - `shift()`: Removes the first element of the array.
     - `unshift()`: Adds an element to the beginning of the array.
     - `map()`: Creates a new array by applying a function to each element of the array.
       ```javascript
       let squared = numbers.map(num => num * num);
       console.log(squared); // [1, 4, 9, 16, 25]
       ```
</details>
JavaScript's data types provide the foundation for manipulating and storing data within programs. Understanding these data types and how to work with them effectively is crucial for writing robust and efficient JavaScript code.

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



