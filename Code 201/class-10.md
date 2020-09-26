## Duckett JS Chapter 10: Error Handling and Debugging (pg 449-486)
 
*JavaScript can be hard to learn and everyone makes mistakes when writing it. This chapter will help you learn how to find the errors in your code. It will also teach you how to write scripts that deal with potential errors gracefully.*
 
*Remember:* javaScript is like problem solving, you're not always going to get it right the first time, but you can develop skills to find the issues. Also, you can create instructions for your computer to follow to help you find the issues in your code. (*linter*)
 
### Tools to assist with debugging and error handling:
- The Console and Developer Tools
- Common Problems (missing punctuation, misspelled variables and elements)
- Handling Errors - How code can deal with potential errors gracefully.
 
*The javaScript interpreter processes one line of data at a time. This creates a stack moving top to bottom.*
 
- Whenever a statement calls a new code block in, this goes to the top of the stack
- Once the new code block runs, the interpreter will return to the step that it was on.
- Every time a new item is added to the stack, it creates new execution context.
- Variables defined in a function are only available to that function.
- If a variable is called additional times, the value of the variable may change.
- When calling a new statement, the current statement is effectively placed on hold until the called statement has finished running.
 
*Functions of javaScript are said to have **lexical scope**. This means that they are linked to the object in which they are defined.
- The context of the execution, has the scope of the current execution context's variables object, plus the variables object for each parent execution.
- Nesting Doll - Children ask parents for informationin in their variables.
 
- If javaScript generates an error, it then throws an *exception*. At this point, the interpreter stops and looks for *exception-handling code.*
 
 
**When an Er ror object is created, it will contain the following properties:**
- `name` - Type of execution
- `message` - Description
- `fileNumber` - Name of the JavaScript file
- `lineNumber` - Line number of error
 
**There are seven types of built-in error objects in javaScript:**
- Error - Generic error - the other errors are all based upon this error
- Syntax Error - Syntax has not been followed
- ReferenceError - Tried to reference a variable that is not declared/within scope
- TypeError - An unexpected data type that cannot be coerced
- RangeError - Numbers not in acceptable range
- URIError - encodeURI().decodeURI(),and similar methods used incorrectly
- EvalError - eval() function used incorrectly
 
*SyntaxError:*
 
- SYNTAX IS NOT CORRECT - This is caused by incorrect use of the rules of the language. It is often the result of a simple typo.
- MISMATCHING OR UNCLOSED QUOTES - Using both single and double quotes in a string. (Example: document.write('helloWorld");
- MISSING CLOSING BRACKET - Forgetting to either open or close a function (), [], {}, ;, or ,.
- MISSING COMMA IN ARRAY - Would be same for missing ] at the end.
- MALFORMED PROPERTY NAME - It has a space but is not surrounded by quote marks.
 
*ReferenceError:*
 
- VARIABLE DOES NOT EXIST - This is caused by a variable that is not declared or is out of scope.
- VARIABLE IS UNDECLARED - Using a variable that has not been assigned a value.
- NAMED FUNCTION IS UNDEFINED - Function has not been defined, or does not have content.
 
*EvalError:*
 
- INCORRECT USE OF eval() FUNCTION - The eval () function evaluates text through the interpreter and runs it as code. It is rare that you would see this type of error, as browsers often throw other errors when they are supposed to throw an EvalError.
 
*URIError:*
 
- INCORRECT USE OF URI FUNCTIONS - If these characters are not escaped in URIs, they will cause an error: / ? & I : ;
- URI - Uniform Resource Identifier
 
*Type Error:*
 
- VALUE IS UNEXPECTED DATA TYPE - This is often caused by trying to use an object or method that does not exist.
- INCORRECT CASE FOR document OBJECT - Document.write ('Oops!'); - Capital "D" in Document
- INCORRECT CASE FOR write() METHOD - document.Write('Oops!'); - Capital "W" in Write
- METHOD DOES NOT EXIST
var box = {}; // Create empty object
box.@Mi}id ; // Try to access getArea()
- DOM NODE DOES NOT EXIST - var el = document .getElementByid('z');
  .                           el.innerHTML = 'Mango';
 
*RangeError*
 
- NUMBER OUTSIDE OF RANGE - If you call a function using numbers outside of its accepted range.
- CANNOT CREATE ARRAY WITH -1 ITEMS - var anArray = new Array(-1);
- NUMBER OF DIGITS AFTER DECIMAL IN tofixed() CAN ONLY BE 0-20 - var price = 9.99;
-                                                                                                                              price.toFixed(21);
- NUMBER OF DIGITS IN toPrecision() CAN ONLY BE 1-21 - num = 2.3456;
-                                                                                                     num.toPrecision(22);
 
*NaN:*
- NOT AN ERROR - Note: If you perform a mathematical operation using a value that is not a number, you end up with the value of NaN, not a type error.
 
 
 
### HOW TO DEAL WITH ERRORS
 
1. DEBUG THE SCRIPT TO FIX ERRORS
*If you come across an error while writing a script (or when someone reports a bug), you will need to debug the code, track down the source of the error, and fix it.*
 
2. HANDLE ERRORS GRACEFULLY
*You can handle errors gracefully using try, catch, throw, and finally statements.*
 
### A DEBUGGING WORKFLOW
 
*Debugging is about deduction: eliminating potential causes of an error.*
 
*Where is the problem?*
 
1. Look at the error message, it tells you:
  - The relevant script that caused the problem.
  - The line number where it became a problem for the interpreter.
  - Type of Error
 
2. How far into the script did the interpreter execute?

3. Use breakpoints - pause execution and inspect the values stored in variables.

*What exactly is the problem?*

1. Breakpoints allow you to stop the code in intervals to inspect in smaller sections.

2. Break down / break out parts of the script to test in smaller sections to test functionality.
- Write values of variables into the console.
- Call functions from the console to check if they are returning what you would expect them to. 
-  Check if objects exist and have the methods I properties that you think they do.

3. Check the number of parameters for a function, or the number of items in an array.

**Be prepared to do this multiple times, you may fix something just to uncover something else broken!**

 **BROWSER DEV TOOLS & JAVASCRIPT CONSOLE**

 - Use the console in Chrome
 
 *CHROME/ OPERA*

On a PC, press the F12 key or:
1. Go to the options menu (or three line menu icon) 
2. Select Tools or More tools.
3. Select JavaScript Console or Developer Tools
On a Mac press A lt + Cmd + J. Or:
4. Go to the View menu.
5. Select Developer.
6. Open the JavaScript Console or Developer Tools option and select Console.

*INTERNET EXPLORER*

Press the F12 key or:
1. Go to the settings menu in the top-right. 
2. Select developer tools.

*FIREFOX*

On a PC, press Ctrl + Shift + K or: 
1. Go to the Firefox menu.
2. Select Web Developer.
3. Open the Web Console.

On a Mac press Alt + Cmd + K Or: 
1. Go to the Tools menu.
2. Select Web Developer.
3. Open the Web Console.

*SAFARI*

Press Alt + Cmd + C or:
1. Go to the Develop menu.
2. Select Show Error Console.

If the Develop menu is not shown:

1. Go to the Safari menu.
2. Select Preferences.
3. Select Advanced.
4. Check the box that says "Show Develop menu in menu bar."