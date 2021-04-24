# Class 42: Pythonisms

## [Dunder Methods](https://dbader.org/blog/python-dunder-methods)

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.

## Enriching a Simple Account Class
You can enrich a simple Python class with various dunder methods to unlock the following language features:

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)

## Object Initialization: `__init__`
Right upon starting the class you already need a special method. To construct account objects from the Account class you need a constructor which in Python is the `__init__` dunder:

Example:
```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

> The constructor takes care of setting up the object. In this case it receives the owner name, an optional start amount and defines an internal transactions list to keep track of deposits and withdrawals.

## Object Representation: `__str__`, `__repr__`

It’s common practice in Python to [provide a string representation of your object for the consumer of your class](https://dbader.org/blog/python-repr-vs-str) (a bit like API documentation.) There are two ways to do this using dunder methods:

1. `__repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

1. `__str__`: The “informal” or nicely printable string representation of an object. This is for the enduser.

````
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
````

If you don’t want to hardcode "Account" as the name for the class you can also use self.__class__.__name__ to access it programmatically.

If you wanted to implement just one of these to-string methods on a Python class, make sure it’s __repr__.







## [Iterators](https://dbader.org/blog/python-iterators)
## [Generators](https://dbader.org/blog/python-generators)
## [What are Generators](https://realpython.com/lessons/what-are-python-generators/)
## [Decorators](https://realpython.com/primer-on-python-decorators/)

