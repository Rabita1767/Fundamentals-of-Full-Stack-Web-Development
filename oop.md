## What is OOP

**OOP (Object-Oriented Programming)** is a programming paradigm where code is structured using **classes** and **objects**.

---

## Object

An **object** is an entity that encapsulates **data (attributes)** and **functions (methods)**.

**Example:**  
A **Car** is an object that can have properties like `color`, `name`, and methods like `brake()` and `speed()`.

---

## Class

A **class** is a **blueprint** for creating objects.  
It defines the **properties** and **methods** that an object will have.

---

## Why OOP is Necessary

1. **Simplifies complex problems** by breaking them into smaller, connected classes or objects.
2. **Enhances security** through features like _encapsulation_ and _data hiding_.
3. **Increases reusability** — multiple objects can be created from the same blueprint.
4. **Supports flexibility** — features like _inheritance_ and _polymorphism_ allow extending or modifying functionality without breaking existing code.
5. **Improves maintainability** — modular and structured code is easier to update and manage.

---

## Pillars of OOP

1. **Encapsulation**
2. **Inheritance**
3. **Polymorphism**
4. **Abstraction**

## Encapsulation

It is the process of binding data(attribute) and methods(functions) into a single unit or class. It is used to hide internal state pf an object and controlling access from unauthorized and unintended user

## Inheritance

When a new class inherits properties and behaviour (attributes and methods) from an existing class, then it's called Inheritance. The sub class can override existing functionalities or create it's own methods. It increases reusability.

## Polymorphism

Polymorphism stands for "Many Forms". When an interface or methods is implemented with different implementation then it's called polymorphism.
There are teo types of polymorphism:

1. Runtime Polymorphism/Method Overriding
2. Compiletime Polymorphism/Method Overloading

**Runtime Polymorphism/Method Overriding**

When a new class extends an existing class, it inherits the properties and methods from the parent class. If we define a new implementation for a method in the subclass that was already defined in the parent class, it's called Method Overriding. Which method will be executed is determined at the runtime. That's why it's also known as Runtime Polymorphism.

**Compiletime Polymorphism/Method Overloading**

When two or more methods with the same name exists in the same class but with different parameters, it's called Method Overloading. Which method to be executed is decided based on the given arguments. It is done at compile time, so it's called compiletime Polymorphism.

## Abstraction

Abstraction is the process of data hiding. Means , it hides complex implementation and only show the essentials.
It can be achieved through interfaces or abstract classes where a method is mentioned but not implemented. It will be implemented in his inherited classes
