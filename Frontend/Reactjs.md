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
