# Class 38: React 2
---

##  [React - Conditional Rendering]()

In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application.

Conditional rendering in React works the same way conditions work in JavaScript. Use JavaScript operators like `if` or the `conditional operator` to create elements representing the current state, and let React update the UI to match them.

### <u>Element Variables</u>

You can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change.

While declaring a variable and using an `if` statement is a fine way to conditionally render a component, sometimes you might want to use a shorter syntax. There are a few ways to inline conditions in JSX.

### <u>Inline `If` with Logical `&&` Operator</u>

You may `embed expressions in JSX` by wrapping them in curly braces(`{}`). This includes the JavaScript logical `&&` operator. It can be handy for conditionally including an element.

It works because in JavaScript, `true && expression` always evaluates to `expression`, and `false && expression` always evaluates to `false`.

Therefore, if the condition is `true`, the element right after `&&` will appear in the output. If it is `false`, React will ignore and skip it.

Note that returning a falsy expression will still cause the element after `&&` to be skipped but will return the falsy expression. 

### Inline If-Else with Conditional Operator

Another method for conditionally rendering elements inline is to use the JavaScript conditional operator `condition ? true : false`.







##  [React - Lists & Keys]()






##  [React - Forms]()





##  [React - Lifting State]()







##  [React - Composition vs Inheritance]()








##  [Thinking in React]()






## Additional Resources
##  [[Video] Review: Hero Icons]()






##  [Review: React - Comprehensive Guide]()






##  [Review: Heroicons]()






