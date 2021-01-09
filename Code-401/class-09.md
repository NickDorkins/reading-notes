# Class-09: Game of Greed 4

## Enriching Your Python Classes With Dunder (Magic, Special) Methods

![Nina West Magic](https://64.media.tumblr.com/2e397ef451f86fbe94a3409122fd30ff/tumblr_pqxnb8jJ281uruuoqo4_400.gifv)

## What Are Dunder Methods?

In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores.

***Pythonistas adopted the term “dunder methods”, a short form of “double under.”***

Dunder methods let you emulate the behavior of built-in types.

## Special Methods and the Python Data Model

This elegant design is known as the [Python data model](https://docs.python.org/3/reference/datamodel.html) and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

## Enriching a Simple Account Class

You can enrich a simple Python classes with various dunder methods to unlock the following language features:

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)

## Object Initialization: `__init__`

Right upon starting your class you already need a special method.

To construct objects from the class you need a constructor which in Python is the `__init__` dunder.

## Object Representation: `__str__`, `__repr__`

***It’s common practice in Python to [provide a string representation of your object for the consumer of your class](https://dbader.org/blog/python-repr-vs-str) ***


Two ways to do this using dunder methods:

**`__repr__`**: The “official” string representation of an object. This is how you would make an object of the class. The goal of `__repr__` is to be unambiguous.

**`__str__`**: The “informal” or nicely printable string representation of an object. ***This is for the enduser.***

# [Tutorial: Basic Statistics in Python — Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)

At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. 

## From statistics to probability

Probability provides the theory, while statistics provides the tools to test that theory using data. The descriptive statistics, specifically mean and standard deviation, become the proxies for the theoretical. You may ask, “Why would I need a proxy if I can just calculate the theoretical probability itself?” Coin tosses are a simple toy example, but the more interesting probabilities are not so easily calculated.

There are no easy ways to calculate probabilities, so we must fall back on using data and statistics to calculate them. Given more and more data, we can become more confident that what we calculate represents the true probability of these important events happening.

## The data and the distribution

The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics.

![Normal Distribution](https://i.imgur.com/3vDS2Au.png)

## [Intro to Statistics](https://www.youtube.com/watch?v=MdHtK7CWpCQ)

Data Science has evolved over the last several decades to include methods such as machine learning.

Statistics - A collection of procedures and principles for gaining informationin order to make decisions when faced with uncertainty.



















[Statistics Module](https://docs.python.org/3/library/statistics.html)