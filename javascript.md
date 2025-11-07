## What is Javascript and how does it work?

Javascript is a synchronous and single-threaded programming language. When we declare a programming language to be single-threaded it means that language can execute one line of code at a time. Again, when we declare a programming language to be synchronous we mean, that can complete execution of the current task then take on another one. So as javascript is a single-threaded and synchronous programming language, It can execute one line at a time and after completion of that current execution, it starts execution of the next line.

Another interesting fact about javascript is, here everything happens inside an **Execution Context**.

---

### What is an Execution Context?

It's like a container. It has two chamber. One is called **"Memory"** or **"Variable Environment"**. Another is called **"Code"** or **"Thread of Execution"**.

In variable environment, variables and functions are stored in key-value pairs.

---

### Steps of Javascript Code Execution

When a javascript code starts to execute, it follows two steps:

1. **Memory Allocation Phase**
2. **Code Execution Phase**

---

#### Memory Allocation Phase

In Memory allocation phase, memory is allocated for every variables and functions.  
In case of variables, they are initialized with **undefined** and functions are copied into the execution context.

---

#### Code Execution Phase

In second phase called code execution phase, variables are assigned with their actual values and each time a function is invoked, a new execution context is created for that function and it again repeats the same steps.

After completion of the function execution, when the **"return"** keyword is met, the control returns back to where the function was initially invoked.

## Call Stack

As we have already discussed that everything happens in javascript happens inside an Execution Context. In the second phase of the Execution Context, which is known as the execution phase, whenever a new function is invoked, a new execution context is created. Whenever a function execution is completed, the control is set back to the place from where the function was invoked initially. Here, the concept of Call Stack comes in handy. It handles the creation and deletion of Execution Context. When a javascript code starts execution the Global Execution Context is pushed into the stack. In the code execution phase of new function is invoked, thus creates a new execution context, that execution context is pushed inside the call stack and only popped out when the execution of that function is completed.

## JavaScript Hoisting

In JavaScript, variables and functions are conceptually moved at the top of their current scope during the compilation phase, even before the code has started to execute. This is called **hoisting**.

We have already discussed about execution context and its phases. During the **memory allocation phase**, JavaScript variables declared with `var`/`let`/`const` all allocate memory and are hoisted.

- In case of variables declared with `var`, this variable is initialized with `undefined` and attached to the **Global object**.
- In case of `let` or `const`, memory is allocated but **not initialized**, and attached to a separate memory space (**script's lexical environment**). This separate memory space cannot be accessed until a value is initialized to that variable.

So, the time from when a variable declared with `let` or `const` is hoisted to the time it has been initialized with an actual value is called the **Temporal Dead Zone (TDZ)**.

That's why if we try to access a variable declared with `var` before its initialization, we get `undefined`. But in the case of `let`/`const`, we get a **ReferenceError** because they remain in the Temporal Dead Zone. However, all three of them are hoisted.

## Javascript Closure

Functions along with their lexical environment together form a **closure**.

```javascript
function x() {
  var a = 5;
  function y() {
    console.log(a);
  }
  y();
}
x();
```

## Callback Function

In JavaScript, functions are **first-class citizens**.  
A function can be:

- Assigned to a variable
- Passed as an argument
- Returned from another function

When a function is passed as an argument to another function, and that inner function is later invoked inside the outer function to achieve a certain task, it’s called a **callback function**.

---

### Types of Callbacks

There are two types of callbacks:

1. **Synchronous Callbacks**
2. **Asynchronous Callbacks**

It’s important to understand whether a callback is synchronous or asynchronous.

---

### Example

```javascript
let value = 1;

doSomething(() => {
  value = 2;
});

console.log(value);
```

In the above example:

- If the callback is **synchronous**, the value printed will be **2**.
- If the callback is **asynchronous**, the value printed will be **1**, because `console.log` will execute **before** the value changes to 2.

---

### ⚙️ Examples in JavaScript

#### synchronous Callbacks

- `map()`
- `filter()`
- `forEach()`

#### asynchronous Callbacks

- `setTimeout()`
- `setInterval()`
- Network calls (e.g., `fetch`)
- Promises

## Promise in javascript

Promise is an javascript object that represents an eventual completion or failure of an asynchronous task. It is a placeholder for a data that is not currently present but will be available after a certain period of time

It has three states

1. Pending
2. Fulfilled
3. rejected

Promise is used while fetching data from api, reading file or any task that would take time but can't block the main execution thread.

## Web APIs

- setTimeout()
- DOM APIs. Example: document.getElementById
- fetch()
- console

## How does javascript handles asynchronous task with the help of event loop?

Functions like setTimeout, fetch(), console, and DOM APIs are features provided by the browser, known as Web APIs.
The browser also contains a JavaScript engine, which has a Call Stack — a place where JS instructions are executed one by one. If we have the below code snippet

```javascript
console.log("instruction01");
setTimeout(() => {
    console.log("Print after 5 seconds);
}, 5000);
fetch("www.example.com");
console.log("instruction02");
```

Here’s what happens step by step

- console.log("instruction01")
  This line is pushed into the Call Stack and executed immediately by calling the console Web API, which prints the message.

- setTimeout(...)
  The setTimeout function is then pushed into the Call Stack. It’s handled by the browser’s Web API, which sets a timer for 5 seconds.
  The callback inside setTimeout is registered in the Timer Queue and will only be executed after the timer expires.

fetch("https://www.example.com")
The fetch() call is also handled by the Web API. It starts a network request in the background and immediately returns a Promise.
Once the network request finishes, the callback associated with the Promise (like .then()) is placed in the Microtask Queue.

console.log("instruction02")
This line runs immediately after because JavaScript continues executing synchronously while the asynchronous tasks (like the timer and network call) are being handled by the browser.

When asynchronous tasks finish
After the 5 seconds, the setTimeout callback is moved to the Task Queue.
Similarly, once the fetch request is resolved, its Promise callback goes to the Microtask Queue.

Event Loop’s role
The Event Loop constantly checks whether the Call Stack is empty.

If it’s empty, it first takes all callbacks from the Microtask Queue (like resolved Promises) and executes them.

Once the Microtask Queue is cleared, it moves to the Task Queue (like setTimeout) and executes those callbacks next.

This process ensures that asynchronous operations are handled efficiently without blocking the main thread.
That’s how JavaScript — despite being single-threaded — performs non-blocking, asynchronous tasks smoothly with the help of the Event Loop.

## 🧠 What is Prototype Chain in JavaScript?

A **prototype** in JavaScript is basically an **object** from which other objects inherit properties and methods.  
In JavaScript, the concept of **inheritance** is implemented through the **Prototype Chain**.

Every object in JavaScript is internally linked with another object called its **prototype**.

Whenever we look for a property or method in an object:

1. It is first searched directly inside that object.
2. If it’s not found there, JavaScript looks for it inside the object’s prototype.
3. If it’s still not found, the search continues to the prototype of the prototype, and so on.

This process continues until the property or method is found, or the search reaches the end of the prototype chain — which is when the prototype becomes `null`.

When `null` is reached, it means we’ve reached the **end of the prototype chain**.

Functions in JavaScript also have a `prototype` object.  
When we create a function and use it as a constructor to create new objects, those objects are internally linked to the constructor’s prototype. This allows all instances created by the same constructor to share the same properties and methods defined on the constructor’s prototype.

### 🧩 Example

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function () {
  return `Hello, I'm ${this.name}`;
};

const alice = new Person("Alice");

console.log(alice.greet()); // Output: Hello, I'm Alice
console.log(alice.__proto__ === Person.prototype); // true
console.log(Person.prototype.__proto__ === Object.prototype); // true
console.log(Object.prototype.__proto__); // null (end of prototype chain)
```

## What is IIFE

IIFE refers to **"Immediately Invoked Function Expression"**. Here, functions are defined and executed immediately.

```js
(function() {
  var message = "I am Rabita Amin";
  console.log(message); // Output: I am Rabita Amin
})();
console.log(message); // Output: ReferenceError


here, we can see that, the function declaration does not need a name and it's called immediately after the declaration. The difference between a normal function and a IIFE is the way it allocates memory in it's scope. In case of normal function, it allocates memory and in the code execution phase a new execution context is created for that function. But in case of IIFE, as the function is executed when it's defined, it temporarily allocates memory and as soon as the function is executed the execution context is destroyed and memory is freed
```

Here, we can see that the function does not need a name and is called immediately after its declaration.
The main difference between a normal function and an IIFE lies in how memory is allocated within its scope.

In the case of a normal function, memory is allocated, and during the code execution phase, a new execution context is created for that function.
But in the case of an IIFE, since the function is executed immediately after being defined, it allocates memory temporarily. As soon as the function finishes execution, its execution context is destroyed, and the memory is freed.

## First Class Function

In Javascript, Functions are treated as First Class Citizen. A programming language has a First Class Function means Functions are treated as variables here.

1. Functions can be assigned into a variable
2. Functions can be passed as an argument into another function
3. Functions can be retired from another function

```js
const operation = {
  add: (x, y) => {
    return x + y;
  },
  subtraction: (x, y) => {
    return x - y;
  },
};
```

## What is Higher Order Function

A function is said to be a Higher Order Function if it has any of these properties

1. A function can take one or more functions as it's parameters.
2. Another function is returned from a function

Some built in Higher Order Functions are: Map, Filter, Reduce etc
