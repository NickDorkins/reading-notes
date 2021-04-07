# Class 37: React


## ES6 Overview
### [ES6 Syntax and Feature Overview](https://www.taniarascia.com/es6-syntax-and-feature-overview/)


| Keyword | Scope	| Hoisting | Can Be Reassigned | Can Be Redeclared |
| --- | --- | --- | --- | --- |
|var	|Function scope	|Yes|	Yes	|Yes|
|let	|Block scope	|No|	Yes|	No|
|const|	Block scope	|No|	No|	No|

---

**Arrow functions**

The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own `this`, do not have prototypes, cannot be used for constructors, and should not be used as object methods.

---

**Implicit returns**

The `return` keyword is implied and can be omitted if using arrow functions without a block body.

---

**Method definition shorthand**

The `function` keyword can be omitted when assigning methods on an object.

---
---
---


## **React**
### [React - Hello World](https://reactjs.org/docs/hello-world.html)

### Why JSX?
React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.


Embedding Expressions in JSX
In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces:

```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
You can put any valid JavaScript expression inside the curly braces in JSX. For example, 2 + 2, user.firstName, or formatName(user) are all valid JavaScript expressions.

In the example below, we embed the result of calling a JavaScript function, formatName(user), into an `<h1>` element.


```
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
---

**JSX Prevents Injection Attacks** 

It is safe to embed user input in JSX:

```
const title = response.potentiallyMaliciousInput;
// This is safe:
const element = <h1>{title}</h1>;
```

By default, React DOM escapes any values embedded in JSX before rendering them. Thus it ensures that you can never inject anything that’s not explicitly written in your application. Everything is converted to a string before being rendered. This helps prevent XSS (cross-site-scripting) attacks.




### [React - JSX](https://reactjs.org/docs/introducing-jsx.html)


**Updating the Rendered Element**

React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

With our knowledge so far, the only way to update the UI is to create a new element, and pass it to ReactDOM.render().







### [React - Rendering Elements](https://reactjs.org/docs/rendering-elements.html)







### [React - Components & Props](https://reactjs.org/docs/components-and-props.html)






### [React - State & Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)






### [React - Handling Events](https://reactjs.org/docs/handling-events.html)






## Tailwind CSS
### [Utility First CSS](https://tailwindcss.com/docs/utility-first)






### [Tailwind in 15 minutes](https://www.youtube.com/watch?v=6zIuAyLZPH0)






## Next.js
### [Learn Next.js](https://nextjs.org/learn/basics/create-nextjs-app)






### [Why to use Next.js](https://www.youtube.com/watch?v=rtgbaKBhdkk)






