# Read: 03 Flexbox and Templating
 
## Javascript Templating Language and Engine— Mustache.js with Node and Express
### Source: https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2
 
### Javascript Templating
 
- Fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. 
 
- HTML markup, with added templating tags that will either insert variables or run programming logic.
 
- Template engine replaces variables and instances declared in a template file with values at runtime, and convert the template into an HTML file sent to the client.
 
### Mustache
 
Mustache is often referred to as “logic-less” because there are no `if` statements, `else` clauses, or `for` loops, there are only tags. 
 
Some tags are replaced with a value, some nothing, and others a series of values.
 
**Uses**
- HTML
- Config Files
- Source Code
- Etc.
 
### mustache.js
 
- Implements mustache template system in JS.
 
- Supports various languages
> Don't need a separate templating system server side.
 
```
Mustache.render(“Hello, {{name}}”, { name: “Sherlynn” });
// returns: Hello, Sherlynn
```
 
Mustache is a specification for a templating language, not a template engine.
> Write templates according to the Mustache Specification, then compile it in a templating engine, this will render your output.
 
<!-- ![Templating-Example](https://miro.medium.com/max/700/1*LbqYj87xlazySm6wE0Q2lA.png){:height="50%" width="50%"} -->
 
If using Node and Express - mustache-express
 
To install:
With Yarn:
```
$ yarn add mustache-express
```
or with NPM:
```
$ npm install mustache --save
```
Configure mustache-express in your server.js/app.js/index.js file:
```
var mustacheExpress = require('mustache-express');
 
// Register 'mustache' extension with the Mustache Express
app.engine('html', mustacheExpress());
 
app.set('view engine', 'html');
app.set('views', _dirname + '/src/views');
```
 
Create a views folder and add some html view templates (e.g. hello.html):
 
![template code block](https://miro.medium.com/max/700/1*FRcL9NQHI7Cvi2ELLmzJGQ.png)
 
Then in the router configuration, use res.render(TEMPLATE_NAME, JSON_DATA). Example:
```
res.render('hello', {"name": "Sherlynn"})
```
 
>Parameter 1: ‘hello’ refers to the hello.html file 
> 
>Parameter 2: The JSON data
 
Example of passing in a variable representing the data:
```
var nameObject = {"name": "Sherlynn"}
 
res.render('hello', nameObject)
```



## A Complete Guide to Flexbox
 
Source: https://css-tricks.com/snippets/css/a-guide-to-flexbox/
 
**display** - defines a flex container; inline or block depending on the given value. 
> It enables a flex context for all its direct children.
 
**order** - controls the order in which items appear in the flex container
 
**flex-direction** - the direction flex items are placed in the flex container.

> - `row` (default): left to right in `ltr`; right to left in `rtl`
> - `row-reverse`: right to left in `ltr`; left to right in `rtl`
> - `column`: same as row but top to bottom
> - `column-reverse`: same as `row-reverse` but bottom to top
 
**flex-grow** - dictates what amount of the available space inside the flex container the item should take up.
>
>```
>.item {
>  flex-grow: 4; /* default 0 */
>}
>
>This example illustrates that the element with the class "item" will be 4 times larger
> than the other children inside the same section.
>```

> 
>NOTE: NEGATIVE NUMBERS ARE INVALID 
>
 
**flex-wrap** - flex items will wrap when exceeding the edge of the parent container.

> - `nowrap` (default): all flex items will be on one line
> - `wrap`: flex items will wrap onto multiple lines, from top to bottom.
> - `wrap-reverse`: flex items will wrap onto multiple lines from bottom to top.
 
**flex-shrink** - defines the ability for a flex item to shrink if necessary.

> 
>NOTE: NEGATIVE NUMBERS ARE INVALID 
>
 
**flex-flow** - shorthand for the `flex-direction` and `flex-wrap` properties
 
**flex-basis** - defines the default size of an element before the remaining space is distributed. 
 
**justify-content** - defines the alignment along the main axis.

> This will distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size.

> - `flex-start` (default): items are packed toward the start of the flex-direction.
> - `flex-end`: items are packed toward the end of the flex-direction.
> - `start`: items are packed toward the start of the writing-mode direction.
> - `end`: items are packed toward the end of the writing-mode direction.
> - `left`: items are packed toward left edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
> - `right`: items are packed toward right edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
> - `center`: items are centered along the line
> - `space-between`: items are evenly distributed in the line; first item is on the start line, last item on the end line
> - `space-around`: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
> - `space-evenly`: items are distributed so that the spacing between any two items and the space to the edges are equal.

> NOTE: Not all of these work in every browser.
>
> Check MDN's Detailed Charts for reference: https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content
 
**flex** - shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined.

>It is recommended that you use this shorthand property rather than set the individual properties. The shorthand sets the other values intelligently.

**align-self** - allows the default alignment to be overridden for individual flex items.
> Note that `float`, `clear` and `vertical-align` have no effect on a flex item.

**align-items** - defines the default behavior for how flex items are laid out along the cross axis on the current line.

> - `stretch` (default): stretch to fill the container (still respect min-width/max-width)
> - `flex-start` / `start` / `self-start`: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the `flex-direction` rules or the `writing-mode` rules.
> - `flex-end` / `end` / `self-end`: items are placed at the end of the cross axis. The difference again is subtle and is about respecting `flex-direction` rules vs. `writing-mode` rules.
> - `center`: items are centered in the cross-axis
> - `baseline`: items are aligned such as their baselines align

>The `safe` and `unsafe` modifier keywords can be used in conjunction with all the rest of these keywords, and deal with helping you prevent aligning elements such that the content becomes inaccessible.

> Browser Support: https://developer.mozilla.org/en-US/docs/Web/CSS/align-items

**align-content** - aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

> - `normal (default): items are packed in their default position as if no value was set.
> - `flex-start` / `start`: items packed to the start of the container. The (more supported) `flex-start` honors the `flex-direction` while `start` honors the `writing-mode` direction.
> - `flex-end` / `end`: items packed to the end of the container. The (more support) `flex-end` honors the `flex-direction` while end honors the `writing-mode` direction.
> - `center`: items centered in the container
> - `space-between`: items evenly distributed; the first line is at the start of the container while the last one is at the end
> - `space-around`: items evenly distributed with equal space around each line
> - `space-evenly`: items are evenly distributed with equal space around them
> - `stretch`: lines stretch to take up the remaining space

>The `safe` and `unsafe` modifier keywords can be used in conjunction with all the rest of these keywords, and deal with helping you prevent aligning elements such that the content becomes inaccessible.

> Browser Support: https://developer.mozilla.org/en-US/docs/Web/CSS/align-items




## FLEXBOX FROGGY
Source: https://flexboxfroggy.com/ - Complete Tutorial

```
flex-direction: row-reverse;
justify-content: flex-end;
```
Flips everything in reverse order to the right and then justifies it back to the left.

```
flex-direction: column;
justify-content: flex-end;
```
Puts eveything in a column and then pushes it to the bottom of the container

```
flex-flow:column-reverse wrap-reverse;
justify-content:center;
align-content:space-between;
```
1. reverse order and wrap content
2. center vertically
3. applied even space between content pushing everything to the left and right

## mustache.js - Logic-less {{mustache}} templates with JavaScript
Source: https://github.com/janl/mustache.js