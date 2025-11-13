## How does React work?

React is a Javascript library used to design the user Interface. It is used to build a component based architecture and Single Page Application. A single html is loaded with dynamic web content

React utilizes the concept of Virtual Document Object Model(VDOM). Here are the steps describing how react works

1. Initial Render and VDOM creation
   When a react application loads on our computer for the first time a Virtual DOM is created which mirrors the actual DOM. A virtual DOM is a in-memory light-weight representation of the actual DOM. It's a tree based architecture with light-weight javascript objects.

2. State/Props Change
   When a state/props change in a react component instead of directly updating the actual DOM, React creates another new VDOM for the newly updated view.

3. Diffing Algorithm
   A efficient "Diffing Algorithm" is used to compare the changes between the new VDOM and the previous VDOM(snapshot from the previos state) and changes are detected. This algorithm efficiently detects changes by traversing nodes to nodes

4. Reconciliation and Batch Updates
   After detecting the changes, React calculates the minimal set of changes required to update the real DOM. This process is known as reconciliation.

5. Updating the Real DOM
   Finally, React applies these minimal, batched changes to the actual browser DOM. The browser then only has to recalculate the layout and repaint the affected areas, which is much faster than processing extensive changes or full re-renders, resulting in a smooth and responsive user interface.

## Why Do We Use Redux?

Redux is used in many JavaScript applications to manage and maintain the global state of an app efficiently.  
It provides a **centralized store** that holds the state of the entire application. This is especially useful in **medium to large-scale projects**, where the same data needs to be accessed or modified by multiple components. Instead of managing data separately in each component, Redux allows us to store it globally, making it accessible from any part of the component tree.

Another major reason to use Redux is to **avoid props drilling**. When data needs to be passed from a top-level component to deeply nested child components, props drilling can make the code messy and inefficient. Redux solves this problem by allowing components to directly access the required data from the global store.

Additionally, Redux enforces **predictable and structured state updates**. Since we define reducers—which are functions that specify how the state should change—Redux ensures that state mutations follow strict, predictable rules. This helps maintain consistency and makes debugging easier.

## Props and State

Props and State are two fundamental concept for data management in React.

**Props** Props are read-only immutable piece of data passed from parent component to child component. Props can only be updated within the parent component. It increases the component's reusibilituy.

**State** State are mutable data in react. They are created and managed within components. States are updated using setState in class component and useState in Functional component.

## Difference Between `<div>` Tag and `<>` (React Fragment)

The HTML `<div>` tag is normally used for **layout** or **styling** purposes.  
In contrast, the **React Fragment** syntax (`<>...</>`) is a special feature provided by React that allows grouping multiple child elements **without creating an extra node** in the DOM.

The main difference between a `<div>` tag and a React Fragment is that:

- A `<div>` **creates an extra node** in the DOM tree.
- A React Fragment **does not create any additional node**, keeping the DOM structure cleaner and more efficient.

## What is Create-react-app

create-react-app is a pre-configured official tool created by facebook for setting up react projects. It provides a development environment with necessary tools like webpack and babel. It uses webpack as it's module bundler and bable as it's javascript compiler under the hood. It bundles up the whole application before serving it to the server during it's initial startup, which makes the initial starup or hot module replacement to be slow

## How Does Create React App Work?

Create React App (CRA) uses **Webpack** as its module bundler.

Suppose we have a `utils.js` file that’s imported into `App.js`, and `App.js` is imported into `index.js`. When we run the application using the `npm start` command, Create React App starts from the **entry point (`index.js`)** and builds a **dependency graph** — a map of all the files and modules the application needs (including React libraries and third-party dependencies).

Webpack then **bundles all these modules into a single optimized JavaScript file**, typically named `bundle.js`. This file is then served to the browser.

Because CRA waits until the bundling process is complete before serving the app, the user won’t see anything in the browser until this process finishes.

---

## How Does Vite Work?

Vite is a **modern, lightweight, and faster build tool** that leverages the **native ES module** feature of modern browsers.

When we run `npm run dev`, the Vite development server starts almost instantly. It serves the `index.html` file directly, and when the browser requests the script file mentioned inside it (usually `main.js` or `main.jsx`), Vite processes and returns it.

If that file contains any import statements, the browser makes additional requests to the Vite server for those imported modules. Vite only processes and serves the files that are **actually requested**, rather than bundling the whole app upfront.

As a result, the development server starts much faster, and developers can see updates in the browser **almost immediately**.

---

### ✅ Summary

| Tool                 | How It Works                                   | Speed          | Uses Bundling?                                       |
| -------------------- | ---------------------------------------------- | -------------- | ---------------------------------------------------- |
| **Create React App** | Bundles all files first using Webpack          | Slower startup | ✅ Yes                                               |
| **Vite**             | Serves modules on-demand via native ES imports | ⚡ Much faster | ⚙️ Not initially (uses bundling only for production) |
