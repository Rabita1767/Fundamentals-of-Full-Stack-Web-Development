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
