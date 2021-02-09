# Class 19: Automation

## [Python Regular Expressions Tutorial](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)

---

Search engines, search and replace tools of word processors and text editors - all use regular expressions to complete their tasks.

Regex is used to help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

---

Following topics covered:

- See how [basic/ordinary](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#BasicChar) characters are used for performing matches

- [Wild or special](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#WildChar) characters 

- Using [repetitions](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#repetitions) in your regular expressions

- Learn how to create [groups and named groups](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#group) within your search for ease of access to matches 

- Concept of [greedy vs. non-greedy matching](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#greedy).


> ## [Quick Look Summary Table](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#table)

---

Dictionary:

- [Compilation Flags](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#flags)

- [Ordinary characters](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#BasicChar) - match themselves exactly and do not have a special meaning in their regular expression syntax.

- r - Raw string literal - changes how the string literal is interpreted meaning literals are stored as they appear.
---

Start with importing the Python library that supports Regex:

```
import re
```

## Basic Patterns: Ordinary Characters

Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax.

> Ordinary Characters are standard alpha-numeric characters. 0-9, a-z, and A-Z

<br>

The `match()` function returns a match object if the text matches the pattern. Otherwise, it returns `None`.


Example:

`(\)` is just a backslash when prefixed with an `r` rather than being interpreted as an escape sequence.

> Sometimes, the syntax involves backslash-escaped `(\)` characters, and to prevent these characters from being interpreted as escape sequences; you use the raw `(r)` prefix.










































<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## [shutil](https://pymotw.com/3/shutil/)


## [Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)


## [Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)


## [Watchdog](https://pythonhosted.org/watchdog/)