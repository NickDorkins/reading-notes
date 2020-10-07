# Read: 04 Responsive Web Design and Regular Expressions
 
## CSS Grid Garden
Source: https://cssgridgarden.com/
 
- `grid-column` - 
- `grid-column-start` - 
- `grid-column-end` - 
- `grid-row` - 
- `grid-row-start` - 
- `grid-row-end` - 
- `grid-area` - 
- `span` - 
- `order` - 
 
```
#garden {
  display: grid;
grid-template: 1fr 50px / 1fr 4fr;
}
```
Still cannot understand how this one works, I had to look up the solution due to being stuck for 15 minutes.
 
## Regex
Source: https://regexr.com/
 
| Character classes |  |
| --- | --- |
| . | any character except newline |
| \w\d\s | word, digit, whitespace |
| \W\D\S | not word, digit, whitespace |
| [abc] | any of a, b, or c |
| [^abc] | not a, b, or c |
| [a-g] | character between a & g |
 
| Anchors |  |
| --- | --- |
| ^abc$ | start / end of the string |
| \b\B | word, not-word boundary |
 
| Escaped characters |  |
| --- | --- |
| \.\*\\ | escaped special characters |
| \t\n\r | tab, linefeed, carriage return |
 
| Groups & Lookaround |  |
| --- | --- |
| (abc) | capture group |
| \1 |  backreference to group #1 |
| (?:abc) | non-capturing group |
| (?=abc) | positive lookahead |
| (?!abc) | negative lookahead |
 
| Quantifiers & Alternation |  |
| --- | --- |
| a*a+a? | 0 or more, 1 or more, 0 or 1 |
| a{5}a{2,} | exactly five, two or more |
| a{1,3} | between one & three |
| a+?a{2,}? | match as few as possible |
| ab|cd | match ab or cd |
 
## Regex tutorial — A quick cheatsheet by examples
Source: https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
 
## Basic topics
 
| Anchors — ^ and $ |  |
| ---| --- |
| ^The | matches any string that starts with The |
| end$ | matches a string that ends with end |
| ^The end$ | exact string match (starts and ends with The end) |
| roar | matches any string that has the text roar in it |

<br>
 
| Quantifiers — *, +, ?, and {} |  |
| --- | --- |
|abc* | matches a string that has ab followed by zero or more c |
| abc+ |  matches a string that has ab followed by one or more c |
| abc? | matches a string that has ab followed by zero or one c |
| abc{2} | matches a string that has ab followed by 2 c |
| abc{2,} | matches a string that has ab followed by 2 or more c |
| abc{2,5} | matches a string that has ab followed by 2 up to 5 c |
| a(bc)* | matches a string that has a followed by zero or more copies of the sequence bc |
| a(bc){2,5} | matches a string that has a followed by 2 up to 5 copies of the sequence bc |
 
<br>

| OR operator — `|` or [] |  |
| --- | --- |
| a(b`|`c) |     matches a string that has a followed by b or c (and captures b or c) |
| a[bc] |      same as previous, but without capturing b or c |
 
<br>

| Character classes — \d \w \s and . |  |
| --- | --- |
| \d | matches a single character that is a digit |
| \w | matches a word character (alphanumeric character plus underscore) |
| \s | matches a whitespace character (includes tabs and line breaks) |
| . | matches any character |
 
<br>

| Flags |   |
| --- | --- |
| g (global) | does not return after the first match, restarting the subsequent |
|  |searches from the end of the previous match |
| m (multi-line) | when enabled ^ and $ will match the start and end of a line, |
|  | instead of the whole string |
| i (insensitive) | makes the whole expression case-insensitive |
|  | (for instance /aBc/i would match AbC) |
 
## Intermediate topics
 
| Grouping and capturing — () |  |
| --- | --- |
| a(bc) | parentheses create a capturing group with value bc  |
| a(?:bc)* | using ?: we disable the capturing group |
| a(?<foo>bc) | using ?<foo> we put a name to the group |
 
| Bracket expressions — [] |  |
| --- | --- |
| [abc] | matches a string that has either an a or a b or a c 
| --- | the same as a|b|c |
| [a-c] | same as previous |
| [a-fA-F0-9] | a string that represents a single hexadecimal digit, case insensitively |
| [0-9]% | a string that has a character from 0 to 9 before a % sign |
| [^a-zA-Z] | a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression |
 
## Regular Expressions Tester
Source https://regex101.com/
 
## CSS-Tricks: A Complete Guide to Grid
Source: https://css-tricks.com/snippets/css/complete-guide-grid/
 
## Common Responsive Layouts with CSS Grid (and some without!)
Source: https://medium.com/samsung-internet-dev/common-responsive-layouts-with-css-grid-and-some-without-245a862f48df
 
### Large Image followed by articles
- https://grid-cats.glitch.me/ — Demo
- https://glitch.com/edit/#!/grid-cats — Code
 
### The Full Page Image Gallery
- https://cat-grid.glitch.me/ — Example
- https://glitch.com/edit/#!/cat-grid — Code
 
### Card Layout
- https://card-layout.glitch.me/ — Example
- https://glitch.com/edit/#!/card-layout — Code
 
### The Holy Grail Layout (with no set heights!)
- https://grid-grail.glitch.me/ — Example
- https://glitch.com/edit/#!/grid-grail — Code