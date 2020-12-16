# Objects/Recursion/Pytest:Fixtures and Coverage

## Classes and Objects

Source: [Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)

**Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.**

## Accessing Object Variables

You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class.

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
```
> Notice that `myobjectx` and `myobjecty` both call the class of `MyClass()`


## Accessing Object Functions

To access a function inside of an object you use notation similar to accessing a variable.

> You can now call specific parts of that class as a variable using dot notation (Note: the previous class code block)
---
---
## Thinking Recursively

Source: [Thinking Recursively](https://realpython.com/python-thinking-recursively/)

>“Of all ideas I have introduced to children, recursion stands out as the one idea that is particularly able to evoke an excited response.”
>
>— Seymour Papert, Mindstorms

**Iterative code will loop through each instance of a given input (i.e. array) and perform the function on each individual value of the input.**

- **Recursive code will assess the input values and check the edge cases first, is this a single value or a long list of values?**
    - If the list is short iterate and return value
    - If the list is long start splitting the list into smaller sections and checking values. 
    - If the first split does not return the value expected, continue to split the values into smaller sections until the value is found.

    ![RecursionExample](https://i.pinimg.com/originals/3a/64/55/3a6455ecfd1896e6364e8463e388ca18.gif)

    
## Recursive Functions in Python

**A recursive function is a function defined in terms of itself via self-referential expressions**

> This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case.

### Recursion Example:
```
def factorial_recursive(n):
    # Base case: 1! = 1
    if n == 1:
        return 1

    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial_recursive(n-1)
```
### Returned Value:
```
>>> factorial_recursive(5)
120
```

### Visual Explaination

![Recursion Visual](https://files.realpython.com/media/stack.9c4ba62929cf.gif)

## Maintaining State

**When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:**

- Thread the state through each recursive call so that the current state is part of the current call’s execution context

- Keep the state in global scope

### Threading Example:
```
def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)
```
### Returned Value:
```
# Pass the initial state
>>> sum_recursive(1, 0)
55
```
### Here’s how you maintain the state by keeping it in global scope:

```
# Global mutable state
current_number = 1
accumulated_sum = 0


def sum_recursive():
    global current_number
    global accumulated_sum
    # Base case
    if current_number == 11:
        return accumulated_sum
    # Recursive case
    else:
        accumulated_sum = accumulated_sum + current_number
        current_number = current_number + 1
        return sum_recursive()
```
### Returned Value:
```
>>> sum_recursive()
55
```

## Recursive Data Structures in Python

**A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure.**

### Recursive Data Structure Example:
```
# Return a new list that is the result of
# adding element to the head (i.e. front) of input_list
def attach_head(element, input_list):
    return [element] + input_list
```

### Return Value Step-By-Step:
```
attach_head(1,                      # Will return [1, 46, -31, "hello"]
  attach_head(46,                   # Will return [46, -31, "hello"]
     attach_head(-31,               # Will return [-31, "hello"]
        attach_head("hello", [])))) # Will return ["hello"]
```
### Returned Value:
```
[1, 46, -31, 'hello']

```

### Recursive Data Structure Visual:
![### Recursive Data Structure Visual](https://files.realpython.com/media/list.3df62a89243d.gif)

1. Starting with an empty list, you can generate any list by recursively applying the attach_head function, and thus the list data structure can be defined recursively as:

            +---- attach_head(element, smaller list)
        list = +
            +---- empty list
        
2. Recursion can also be seen as self-referential function composition. We apply a function to an argument, then pass that result on as an argument to a second application of the same function, and so on. Repeatedly composing attach_head with itself is the same as attach_head calling itself repeatedly.

## Naive Recursion is Naive

> A Naive recursion algorithm is usually the most obvious solution when one is asked a problem. It may not be a smart algorithm but will probably get the job done (...eventually.) 
>
> Source: [What is a “naive” algorithm?](https://stackoverflow.com/questions/5700575/what-is-a-naive-algorithm-and-what-is-a-closed-form-solution)

Naively following the recursive deﬁnition of the nth Fibonacci number was rather inefficient. This can cause us to unnecessarily recompute values. 










---
---
## Pytest Fixtures and Coverage

Source: [Pytest Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)