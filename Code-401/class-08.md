# Class-08: Game of Greed 3

## [List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

List comprehensions provide a concise way to create lists.

It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses. The expressions can be anything, meaning you can
put in all kinds of objects in lists.

The result will be a new list resulting from evaluating the expression in the
context of the for and if clauses which follow it.

The list comprehension always returns a result list.

**Example of standard list creation:**
```
new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))
```

**Example of List Comprehension:**
```
new_list = [expression(i) for i in old_list if filter(i)]
```

> Notice the code is DRY and runs as one line, also, the append method has been removed.

## Syntax

The list comprehension starts with a `[` and `]`, square brackets, to help you remember that the
result is going to be a list.

**The basic syntax uses square brackets.**

```
[ expression for item in list if conditional ]
```

**This is equivalent to:**

```
for item in list:
    if conditional:
        expression
```
---
**Example:**

```
new_list = [expression(i) for i in old_list if filter(i)]
```
---

| Code | Functionallity |
| --- | --- |
| new_list | The new list (result). |
| expression(i) | Expression is based on the variable used for each element in the old list. |
| for i in old_list | The word for followed by the variable name to use, followed by the word in the old list. |
| if filter(i) | Apply a filter with an If-statement. |

Example of how to visually break down the list comprehension:

```
new_range = [i * i for i in range(5) if i % 2 == 0]
```

The above code equates to:  *result* = [*transform* *iteration* *filter* ]

> The `*` operator is used to repeat. The filter part answers the question if the
item should be transformed.


## [Primer on Python Decorators](https://realpython.com/primer-on-python-decorators/)

***Decorators wrap a function, modifying its behavior.***


**Example:**
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

def say_whee():
    print("Whee!")

say_whee = my_decorator(say_whee)
```
## Syntactic Sugar!

![Harry Styles and Danny DeVito](https://media2.giphy.com/media/5xaOcLEsWZVbgoVCqbe/200w.webp?cid=ecf05e4752d0rdiyewgf0q1x5nmuj2y265lypx6xe4ulard4&rid=200w.webp)

The way you decorated `say_whee()` above is a little clunky.  In addition, the decoration gets a bit hidden away below the definition of the function.

Python allows you to use decorators in a simpler way with the @ symbol, sometimes called the [“pie” syntax](https://www.python.org/dev/peps/pep-0318/#background).

**Example:**

```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```

> `@my_decorator` is just an easier way of saying `say_whee = my_decorator(say_whee)`. It’s how you apply a decorator to a function.

## Reusing Decorators

Recall that a decorator is just a regular Python function. All the usual tools for easy reusability are available. Let’s move the decorator to its own [module](https://realpython.com/python-modules-packages/) that can be used in many other functions.

**Writing Decorator:**

```
def do_twice(func):
    def wrapper_do_twice():
        func()
        func()
    return wrapper_do_twice
```

**Importing Decoratror:**

```
from decorators import do_twice

@do_twice
def say_whee():
    print("Whee!")
```

**Result:**

```
>>> say_whee()
Whee!
Whee!
```

## Decorating Functions With Arguments

**Example:**

```
from decorators import do_twice

@do_twice
def greet(name):
    print(f"Hello {name}")
```

> Running the above code will raise an error.

```
>>> greet("World")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: wrapper_do_twice() takes 0 positional arguments but 1 was given
```

***The solution is to use `*args` and `**kwargs` in the inner wrapper function. Then it will accept an arbitrary number of positional and keyword arguments.***

**Rewritten to accept positional and keyword arguments:**

```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        func(*args, **kwargs)
    return wrapper_do_twice
```







