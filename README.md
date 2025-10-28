# 🧠 Fundamentals-of-Full-Stack-Web-Development

This repository will serve as a comprehensive resource for understanding the theoretical concepts of full-stack web development. It covers a wide range of topics essential for mastering the fundamentals of full-stack development, including:

- **Data Structures**: Learn about arrays, linked lists, stacks, queues, trees, graphs, and algorithms that form the backbone of efficient programming.
- **Frontend Development**: Explore HTML, CSS, and JavaScript fundamentals, along with modern frontend frameworks like React and Next.js, plus best practices for creating responsive and interactive user interfaces.
- **Backend Development**: Understand server-side programming, APIs, authentication, database connections, and popular backend frameworks like Node.js and Express.js.
- **Databases**: Learn about database basics, SQL, NoSQL, normalization, transactions, and database optimization techniques.
- **OOP (Object-Oriented Programming)**: Grasp the key principles such as classes, objects, inheritance, encapsulation, and polymorphism for writing modular and maintainable code.
- **DevOps**: Understand deployment strategies, CI/CD pipelines, containerization, and cloud services.
- **System Design**: Gain insights into designing scalable, reliable, and maintainable systems.

---

The objective of this repository is to provide a structured and detailed guide for anyone looking to build a strong foundation in full-stack web development. Whether you're a beginner or looking to deepen your knowledge, this repository aims to be your go-to resource.

**Contributions and feedback are welcome** to make this resource even better!

> ⚠️ **Note:** This repository is currently a work in progress. More topics and detailed explanations will be added soon.

## Call Stack

As we have already discussed that everything happens in javascript happens inside an Execution Context. In the second phase of the Execution Context, which is known as the execution phase, whenever a new function is invoked, a new execution context is created. Whenever a function execution is completed, the control is set back to the place from where the function was invoked initially. Here, the concept of Call Stack comes in handy. It handles the creation and deletion of Execution Context. When a javascript code starts execution the Global Execution Context is pushed into the stack. In the code execution phase of new function is invoked, thus creates a new execution context, that execution context is pushed inside the call stack and only popped out when the execution of that function is completed
