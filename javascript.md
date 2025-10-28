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
