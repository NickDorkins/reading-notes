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

- `( . )` - A period. Matches any single character except the newline character.

- `( ^ )` - A caret. Matches the start of the string.

- `($)` - Matches the end of string.

- `[abc]` - Matches a or b or c.

- `[a-zA-Z0-9]` - Matches any letter from (a to z) or (A to Z) or (0 to 9).

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

## Wild Card Characters: Special Characters

**`Special characters` are characters that do not match themselves as seen but have a special meaning when used in a regular expression.**

With the [`search function`](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#search), you scan through the given string/sequence, looking for the first location where the regular expression produces a match.

The [`group function`](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial#group) returns the string matched by the re. You will see both these functions in more detail later.

- `( . )` - A period. Matches any single character except the newline character.

- `( ^ )` - A caret. Matches the start of the string.

- `($)` - Matches the end of string.

- `[abc]` - Matches a or b or c.

- `[a-zA-Z0-9]` - Matches any letter from (a to z) or (A to Z) or (0 to 9).

- `( \ )` - Backslash **`(Super Weird Character)`**

    Use Case 1
    - If the character following the backslash `(\)`is a recognized escape character, then the special meaning of the term is taken.

    Use Case 2
    - If the character following the `(\)` is not a recognized escape character, then the `(\)` is treated like any other character and passed through.

    Use Case 3
    - `(\)` can be used in front of all the metacharacters to remove their special meaning.

- `(\w)` - Lowercase 'w'. Matches any single `letter`, `digit`, or `underscore`.

- `(\W)` - Uppercase 'W'. Matches `any character` not part of \w (lowercase w).

- `(\s)` - Lowercase 's'. Matches a **single** whitespace character like: `space`, `newline`, `tab`, `return`.

- `(\S)` - Uppercase 'S'. Matches any character `not part` of \s (lowercase s).

- `(\d)` - Lowercase d. Matches `decimal digit 0-9`.

- `(\D)` - Uppercase d. Matches any character that is `not a decimal digit`.

- `(\t)` - Lowercase t. Matches `tab`.

- `(\n)` - Lowercase n. Matches `newline`.

- `(\r)` - Lowercase r. Matches `return`.

- `(\A)` - Uppercase a. Matches only at the `start of the string`. Works across multiple lines as well.

- `(\Z)` - Uppercase z. Matches only at the `end of the string`.





















<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## [shutil](https://pymotw.com/3/shutil/)


## [Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)


## [Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)


## [Watchdog](https://pythonhosted.org/watchdog/)