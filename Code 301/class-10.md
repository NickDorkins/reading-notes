# Read: 10 - The Call Stack and Debugging

## MDN web docs: Call Stack
Source: https://developer.mozilla.org/en-US/docs/Glossary/Call_stack

A ***call stack*** is a mechanism for an interpreter to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

- When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.

- Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.

- When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.

- If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.


> The Call Stack is like the "stack" in Magic the Gathering, but it is built in a slightly different way. Once the Call Stack is built, and there are no more functions to run, the interpreter will read them off from the top down. As the interpreter reads off the actions, if necessary, the next action may supercede the previous action. Once the final action is taken, the call stack is empty. 

1. Ignore everything until it reaches the first valid function
2. Add new function to Call Stack
3. Execute code inside function
4. If there is another function within this function, the interpreter will add the new function to the Call stack.
5. Execute code inside new function.
6. The interpreter will continue to do this until it hits the end.
7. The interpreter will then execute the code in the Call Stack from the top down. 
8. Once all of the Calls in the Stack have finished running, the interpreter will continue running to the next lines of code.

![JavaScript Call Stack](https://miro.medium.com/max/700/0*ryPdDzB_jghiVi2e.png)

---

## The JavaScript Call Stack - What It Is and Why It's Necessary
Source: https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/

### The JavaScript engine, is a single-threaded interpreter comprised of a heap and a single call stack. The browser provides web APIs like the DOM, AJAX, and Timers.

**The call stack is primarily used for function invocation. Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.**

**Syncronous** - Each statement in your code is executed one after the other. This means each statement has to wait for the previous one to finish executing.

A call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation.

**Last in, First out** - the last function that gets pushed into the stack is the first to be pop out, when the function returns.

![Stack example in console](https://cdn-media-1.freecodecamp.org/images/zOINLHPC8E56ac8yyINYOFWeImsjM2Wk2rdU)

> In the above example:
> - `thirdFunction()` was called 1st / flagged 3rd error
> - `secondFunction()` was called 2nd / flagged 2nd error
> - `firstFunction()` was called 3rd / flagged 1st error

**Temporarily store**: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

![Call Stack Process](https://cdn-media-1.freecodecamp.org/images/QgR2uIk7tW0YNz0Xm8g0jAPeRFI0e4sCejsv)

> - **Push** - Incoming code from the interpreter
> - **Top** - The newest code that the interpreter has pushed into the Call Stack.
> - **Pop** - The first code read and unloaded from the Call Stack

> Think of yourself standing on a queue, in a grocery store cash point. You can only be attended to after the person in front of you have been attended to. That’s synchronous.

**Stack Overflow** - occurs when there is a recursive function (a function that calls itself) without an exit point. 

> The browser has a maximum stack call that it can accomodate before throwing a stack error.

The key takeaways from the call stack are:
1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.

[GitHub repo of code Samlpes](https://github.com/charlesfreeborn/JS-CallStack-CodeSamples/blob/master/codesamples.mdc)

---

## JavaScript error messages && debugging
Source: https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c

### **Reference errors**

Some reasons that you may see this error:
- Using a variable that is not yet declared 
  - This is a common occurance in hoisted variables as there is a delay between the time that they are declared and the time that they are accessed.
  > This reference error between declaration and access is called **Temporal Dead Zone (TDZ)**.

  > Simple solution: Declare the variable before any declaration is made.

### **Syntax errors**

- Occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

> This can be solved by just fixing the syntax.

### **Ra(n)ge errors**

 - Invalid Length
 - Arrays cannot have negative length
    - Negative lengths can be used to empty an array

### Negative Length Example:
 ```
var foo = [0, 0]

foo.length = foo.length - 2 // (or foo.length - foo.length)

foo // would log [] instead of [0, 0]
 ```

### **Type errors**

This types of error shows up when incompatible types try to access each other (number, string and so on), like accessing a property in an undefined type of variable.

 - Probably the most frequent error in JS, trying to access a property/method, that has not been declared. 

### **Debugging**

Easy ways/tools to debug your code:

- `console.log()` variables affected
  - Open dev tools in browser to see `console.log()`to see declarations

**OR**

- Open JS file in browser
  - Mac = (cmd + o)
  - Win = (Ctrl + o)
- Choose file to debug
- Click line to debug
- Refresh page

If the line you selected was run you will be able to see what has happened before that point and you can try and evaluate the next lines to check if everything is outputting what you are expecting.

> The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.

You can also add conditional breakpoints by right-clicking a previous set breakpoint, which will make your program stop at that point **only if a condition is met**.

> Works great for debugging huge cycles of data.

***Using Node.js with Visual Studio Code you can press the debug tab and add a configuration similar to this:***

![VSCode](https://miro.medium.com/max/700/1*q0ybXMtFlQdnXQuOUNRQSw.png)

>Pair your debugger and breakpoints 

>Useful information to know when debugging:
> - Function/variable name
> - Execution line
> - Scope of parameters
> - Name functions so that you can identify them in the debugger
>   - vague names may give you wrong information.
> - `console.trace()` will allow you to trace the call stack

## Handling errors

- **try...catch** - a method used to make an error be thrown but this time, not “uncaught” so we can send it to an error logging to be checked later and send a fallback to the function so that our code continues without problems.

- try - try the code block that I want to run

- catch - if the code in the try statement fails to run correctly, log the error and keep moving to the next code block.

> You can customize the logging message for the errors so that you knokw where you are having issues.

## Tools to avoid runtime errors

JS is not a compiled language like Java so your errors will happen at runtime, that means that you can only see whatever is wrong with your code after your run it.

Tools to save time debugging:

- [quokka](https://quokkajs.com/) to evaluate your code as you type

- [eslint](http://eslint.org/) to make sure your style guide is consistency and it will grab you an error or two along the way and

- For those of you looking to make JS a more strong typed experience you can check out stuff like [TypeScript](https://www.typescriptlang.org/).

## Conclusion

Being able to read error messages and practising debugging is one of the biggest weapons you have as a developer, do it frequently and with enough time you will notice a great decrease in the time you spend on each error that you find along the way. And remember, before you ACP, remove all the debugging stuff from your code, you don’t want the client or another developer to get stuck on a debugger. 