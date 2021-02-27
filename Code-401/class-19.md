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

- `(r)` - Raw string literal - changes how the string literal is interpreted meaning literals are stored as they appear.


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

---

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

> **TIP:** `^` and `\A` are effectively the same, and so are `$` and `\Z`. Except when dealing with `MULTILINE` mode. 

- `(\b)` - Lowercase b. Matches only the beginning or end of the word.

---

## Repetitions

- `(+)` - Checks if the preceding character appears one or more times starting from that position.

- `(*)` - Checks if the preceding character appears zero or more times starting from that position.

- `(?)` - Checks if the preceding character appears exactly zero or one time starting from that position.

- `{x}` - Repeat exactly `x` number of times.

- `{x,}` - Repeat at least `x` times or more.

- `{x, y}` - Repeat at least `x` times but no more than y times.

> `(+)` and `(*)` qualifiers are said to be greedy. See below for explaination of greedy.

---

## Grouping in Regular Expressions

**The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis `()` are called `groups`. The parenthesis does not change what the expression matches, but rather forms groups within the matched sequence.**

Example:

```
<--- INPUT
statement = 'Please contact us at: support@datacamp.com'
match = re.search(r'([\w\.-]+)@([\w\.-]+)', statement) # <-- Group 
if statement:
  print("Email address:", match.group()) # The whole matched text
  print("Username:", match.group(1)) # The username (group 1)
  print("Host:", match.group(2)) # The host (group 2)
```

```
OUTPUT ---> 
Email address: support@datacamp.com
Username: support
Host: datacamp.com
```

Another way of doing the same is with the usage of `<` `>` brackets instead. This will let you create named groups. `Named groups` will make your code more readable. The syntax for creating named group is: `(?P<name>...)`. Replace the name part with the name you want to give to your group. 

> The `(...)` represent the rest of the matching syntax. See this in action using the same example as before...

> ***TIP:*** You can always access the named groups using numbers instead of the name. But as the number of groups increases, it gets harder to handle them using numbers alone. So, always make it a habit to use named groups instead.

---

## Greedy vs. Non-Greedy Matching

When a special character matches as much of the search sequence (string) as possible, it is said to be a `"Greedy Match"`. 

> It is the normal behavior of a regular expression, but sometimes this behavior is not desired.

Adding `?` after the qualifier makes it perform the match in a non-greedy or minimal fashion; That is, as few characters as possible will be matched.

---

## Function provided by `re`

Regular expressions are handled as strings by Python. However, with `compile()`, you can computer a regular expression pattern into a [regular expression object](https://docs.python.org/3/library/re.html#re-objects).

When you need to use an expression several times in a single program, using `compile()` to save the resulting regular expression object for reuse is more efficient than saving it as a string. This is because the compiled versions of the most recent patterns passed to `compile()` and the module-level matching functions are cached.

- `search(pattern, string, flags=0)` - With this function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match. It returns a corresponding match object if found, else returns None if no position in the string matches the pattern. Note that None is different from finding a zero-length match at some point in the string.

- `match(pattern, string, flags=0)` - Returns a corresponding match object if zero or more characters at the beginning of string match the pattern. Else it returns None, if the string does not match the given pattern.

- **`search()` vs. `match()`**

    - The `match()` function checks for a match only at the beginning of the string (by default)
    - the `search()` function checks for a match anywhere in the string.

- `findall(pattern, string, flags=0)` - Finds all the possible matches in the entire sequence and returns them as a list of strings. Each returned string represents one match.

- `finditer(string, [position, end_position])` - Similar to `findall()` - it finds all the possible matches in the entire sequence but returns regex match objects as an iterator.

> **TIP:** `finditer()` might be an excellent choice when you want to have more information returned to you about your search. The returned regex match object holds not only the sequence that matched but also their positions in the original text.

- sub(pattern, repl, string, count=0, flags=0)
subn(pattern, repl, string, count=0)

    - `sub()` is the substitute function. It returns the string obtained by replacing or substituting the leftmost non-overlapping occurrences of pattern in string by the replacement repl. If the pattern is not found, then the string is returned unchanged.

    - The `subn()` is similar to `sub()`. However, it returns a `tuple` containing the new string value and the number of replacements that were performed in the statement.

- `split(string, [maxsplit = 0])` - This splits the strings wherever the pattern matches and returns a list. If the optional argument maxsplit is nonzero, then the maximum 'maxsplit' number of splits are performed.

- `start()` - Returns the starting index of the match.

- `end()` - Returns the index where the match ends.

- `span()` - Return a tuple containing the (start, end) positions of the match.

## Compilation Flags

Flag Modifiers:

- `IGNORECASE (I)` - Allows case-insensitive matches.

- `DOTALL (S)` - Allows . to match any character, including newline.

- `MULTILINE (M)` - Allows start of string `(^)` and end of string `($)` anchor to match newlines as well.

- `VERBOSE (X)` - Allows you to write whitespace and comments within a regular expression to make it more readable.

---

## [Cleaning Data in Python](https://www.datacamp.com/courses/cleaning-data-in-python)

---
---

## [shutil](https://pymotw.com/3/shutil/)

**The `shutil` module includes high-level file operations such as copying and archiving.**

`copyfile()` copies the contents of the source to the destination and raises `IOError` if it does not have permission to write to the destination file.









<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>



## [Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)


## [Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)


## [Watchdog](https://pythonhosted.org/watchdog/)