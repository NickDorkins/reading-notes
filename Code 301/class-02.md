# jQuery 293-301
 
**jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.**
 
## **jQuery** - A javaScript file that is included in web pages, lets the writer use CSS-style selectors to manipulate the elements using jQuery methods.
 
## Select Elements
 
jQuery is simpler to access elements using it's CSS-style Selectors than it is using DOM queries. These selectors are more powerful and flexible.
 
## Perform Tasks
 
jQuery methods let you update the Dom tree, animate elements (into and out of view), and loop through a set of elements in one line of code.
 
## Handle Events
 
jQuery methods allow you to attach event listeners to selected elements without having to wite fallback code to support older browsers.
 
## **1. Find Elelments using CSS style Selectors**
 
```
$('li.hot)
```
> The jQuery() function has one parameter. (Notice: It uses a CSS Style Selector)
 
> This function finds all  `<li>` elements with the class of **hot**.
 
With jQuery **selectors** perform a similar task to traditional DOM queries, but the syntax is much simpler.
 
You can store jQuery objects in a variable, same as with DOM nodes.
 
You can use jQuery methods and properties to manipulate the DOM nodes that you select.
 
**The jQuery object has many methods that you can use to work with the elements that you select. Methods represent tasks that you would commonly perform with elements.**
 
## **2. Do Something with the elements using jQuery methods**
 
`$('li.hot')` = jQuery object created by the jQuery function
> The object and the elements that it contains are referred to as a **matched set** or a **jQuery selection**.
 
`.` - Member operator 
> Indicates that the **method on the right** should update the elements in the **jQuery object on the left**.
 
`addClass('complete")` = jQuery method of the jQuery object
> In this example the method adds a new value to the **class** attribute. 
 
`'complete'` = parameters
> Provides details about how to update the elements .
```
$('li.hot').addClass('complete');
```
-------------------------------------------------------------------
```
1. <body>
2.     <div id="page">
3.         <hl id=" header">List</hl>
4.         <h2>Buy groceries</h2>
5.         <ul>
6.             <li id="one" class="hot"><em>fresh</em> figs</li>
7.             <li id="two" class="hot">pine nuts</li>
8.             <li id="three" class="hot">honey</li>
9.             <li id="four">balsamic vinegar</li>
10.        </ul>
11.    </div>
12.    <script src="js/jquery-1.11.0.js"></script>
13.    <script src="js/basic-example.js"></script>
14 </body> 
```
In order to use jQuery, the first thing you need to do is include the jQuery script in your page. You can see that it is included before the closing `</body>` tag. (line 12)
 
Next, you must add the JavaScript file that has all of the jQuery selectors and metods to update your HTML page. (line 13)
 
### **Note:** You want jQuery to load before your JavaScript so always add your jQuery `<script>` tag before JavaScript `<script>` tag.
 
### **Note:** `.min.js` means that all unnecessary spaces and carriage returns have been removed.
 
### Example of `.min.js`
```
<body> <div id="page"> <hl id=" header">List</hl> <h2>Buy groceries</h2> <ul> <li id="one" class="hot"> <em>fresh</em> figs</li> <li id="two" class="hot">pine nuts</li> <li id="three" class="hot">honey</li> <li id="four">balsamic vinegar</li> </ul> </div> <script src="js/jquery-1.11.0.min.js"></script> <script src="js/basic-example.js"></script> </body> 
```
 
## Why Use jQuery? 
 
***jQuery does not do anything that JavaScript cannot do, it's just a simpler way to write the same functions as JavaScript. jQuery is just a JavaScript file and has shown that due to it's simplicity over 25% of the sites on the web have used it for their pages.***
 
**jQuery Motto:** - "Write less, do more."
 
This motto exists because you can achieve the desired results in less lines of code with jQuery as you can with pure JavaScript.
 
Perks of jQuery:
- Simple Selectors
- Common Tasks in Less Lines of Code
- Cross-Browser Compatibility
 
## Finding Elements (Pg. 302 - 305)
---
 | **BASIC SELECTORS**  |   **HIERARCHY**    |  **BASIC FILTERS**    |  **CONTENT FILTERS**  | 
 |   ---     |   ---     |   ---     |   ---     | 
 |  *    |  ancestor descendant  |  : not (selector)     |  :contains('text ')   | 
 |  element  |  parent > child   |  :first   |   :empty  | 
 |   #id     |  previous + next  |  : last   |  :parent  | 
 |   .class      |  previous - s ib Zings    |  :even    |  :has (selector)  | 
 |  selector1, selector2     |   ---     |  :odd     |   ---     | 
 |   ---     |   ---     |  :eq(index)   |   ---     | 
 |   ---     |   ---     |  :gt(index)   |   ---     | 
 |   ---     |   ---     |  : lt(index)  |   ---     | 
 |   ---     |   ---     |  :header  |   ---     | 
 |   ---     |   ---     |  :animated    |   ---     | 
 |   ---     |   ---     |  :focus   |   ---     | 
---
 

---
 | **VISIBILITY FILTERS** | **CHILD FILTERS**    |  **ATTRIBUTE FILTERS**    |  **FORM**     | 
 | --- | --- | --- | --- |
 |  :hidden  |  :nth-child (expr)    |  [attribute]  |  :input   | 
 |  :visible     |  :first-child     |  [attribute='value']  |  :text    | 
 |   ---     |  :last -child     |  [attribute!='value']     |  :password    | 
 |   ---     |  :only-child  |  [attributeA='value']     |  :radio   | 
 |   ---     |   ---     |  [attribute='value']  |  :checkbox    | 
 |   ---     |   ---     |  [attribute*='value']     |  :submit  | 
 |   ---     |   ---     |  [attribute`|`='value'] |    :image   | 
 |   ---     |   ---     |  [attribute-='value']     |  :reset   | 
 |   ---     |   ---     |  [attribute]  [attribute2]    |  :button  | 
 |   ---     |   ---     |   ---     |  :file    | 
 |   ---     |   ---     |   ---     |  :selected    | 
 |   ---     |   ---     |   ---     |  :enabled     | 
 |   ---     |   ---     |   ---     |  :disabled    | 
 |   ---     |   ---     |   ---     |  :checked     | 
 ---
 ---
 
 | **GET / CHANGE CONTENT** | Page | **ELEMENTS** | Page | **ATTRIBUTES ** | Page | **FORM VALUES ** | Page |
| --- | --- | --- | --- | --- | --- | --- | --- |
| .html() | 316 | .before() | 318 | .attr() | 320 | .val() | 343 |
| .text() | 316 | .after() | 318 | .removeAttr() | 320 | isNumeric() | 343 |
| .replaceWith() | 316 | .prepend() | 318 | .addClass() | 320 | --- | --- |
| .remove | 316 | .append() | 318 | .removeClass() | 320 | --- | --- |
| --- | --- | .remove() | 346 | .css() | 322 | --- | --- |
| --- | --- | .clone() | 346 | --- | --- | --- | --- |
| --- | --- | .unwrap() | 346 | --- | --- | --- | --- |
| --- | --- | .detach() | 346 | --- | --- | --- | --- |
| --- | --- | .empty() | 346 | --- | --- | --- | --- |
| --- | --- | .add() | 338 | --- | --- | --- | --- |
---
---
 
| **GENERAL** | Page | **FILTER/TEST** | Page | **ORDER IN SELECTION ** | Page |
| --- | --- | --- | --- | --- | --- |
| .find() | 336 | .filter() | 338 | .eq() | 340 |
| .closest() | 336 | .not() | 338 | .lt() | 340 |
| .parent() | 336 | .has() | 338 | .gt() | 340 |
| .parents() | 336 | .is() | 338 | --- | --- |
| .children() | 336 | :contains() | 338 | --- | --- |
| .sibHngs() | 336 | --- | --- | --- | --- |
| .next() | 336 | --- | --- | --- | --- |
| .nextAll() | 336 | --- | --- | --- | --- |
| .prev() | 336 | --- | --- | --- | --- |
| .prevAll() | 336 | --- | --- | --- | --- |
---
 
# jQuery Pg. 306-331
 
## A Matched Set / jQuery Selection
 
When you select one or more elements, a jQuery object is returned. **(Elelments = Matched set or jQuery Selection)**
 
```
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```
 
**Single Element** `$('ul')` - This selector picks just the `<ul>` element from the page since there is only one `<ul>` element. 
 
**Multiple Elements** `$('li')` - This selector picks all of the `<li>` elements. Alike sibling elements are given an index number.
 
---
| Single Element |  | Multiple Element|  |
| --- | --- | --- | --- |
| Index | Element Node | Index | Element Node|
| 0 | ul | 0 | li#one.hot |
| --- | --- | 1 | li#two.hot |
| --- | --- | 2 | li#three.hot |
| --- | --- | 3 | li#four |
---
 
## jQuery Objects Store References to Elements
 
**When you create a selection with jQuery, it stores a reference to the corresponding nodes in the DOM tree. It does not create copies of them.**
 
When you create a jQuery selection, the jQuery object holds references to the elements in the DOM.
> It does not create a copy of the elements.
 
When it is said that the **variable** or **object** is storing a reference to something, what it is actually doing is storing the location to a piece of informationin the browsers memory.
 
## Caching jQuery Selections in Variables
 
**A jQuery object stores reference to elements. Caching a jQuery object stores a reference to it in a variable.**
 
To create a jQuery object takes time, processing resources, and memory.
 
The interpreter must:
1. Find the matching nodes in the DOM tree.
2. Create the jQuery object.
3. Store references to the nodes in the jQuery object.
> If code needs to use the same selection more than once, it is better to use that same jQuery object again rather than repeat the process. To do this , you store reference to the jQuery object in a variable.
 
## Looping
 
In plain JavaScript, if you wanted to do the same thing to several elements, you would need to write code to loop through all of the elements you selected.
 
With jQuery, when a selector returns multiple elements, you can update all of them using the one method. There is no need to use a loop. 
 
### Example: (Pg. 310)
```
$('liem').addClass('seasonal') ;
$('li.hot').addClass('favorite'); 
```
> The first selector applies to only one element and the class attribute's new value triggers a CSS rule that adds a calendar icon to the left of the text.
 
> The second selector applies to three elements. The new value added to the class attribute for each of these elements triggers a CSS rule that adds a heart icon on the right-hand side. 
 
The ability to update all of the elements in the jQuery selection is known as **implicit iteration**.
 
When you want to get information from a series of elements, you can use the `.each()` method rather than writing a loop. 
 
## Chaining
 
If you want to use **more than one jQuery method** on the same selection of elements, you can list several methods at a time **using dot notation** to separate each one.
 
```
$('li[id!="one"]').hide().delay(500).fadeln(1400); 
```
> In this one statement, three methods act on the same selection of elements: 
> 
> `hide()` - hides the elements 
> 
> `delay()` - creates a pause 
> 
> `fadeIn()` - fades in the elements 
 
### **Chaining** is more compact than writing each individual method.
 
To make your code easier to read, you can place each new method on a new line: 
 
```
$('li[id!="one"] ')
.hide()
.delay(500)
.fadeln(1400); 
```
> Most methods used to update the jQuery selection can be chained. 
> 
> However the methods that retrieve information from the DOM (or about the browser) cannot be chained.
> 
> It is worth noting that if one method in the chain does not work, the rest will not run either. 
 
## Checking a Page is Ready to Work with
 
**jQuery's `.ready()` method checks that the page is ready fo ryour code to work with.**
 
`$(document)` - creates a jQuery object representing the page
 
`.ready(function())` - When the page is ready the function inside the parentheses of the `.ready()` method is run.
 
```
$(document).ready(function() {
    // Your script goes here
})
```
## GETTING ELEMENT CONTENT
 
**The `.html()` and `.text()` methods both retrieve and update the content of elements.**
 
## `.html()`
 
When this method is used to retrieve information from a jQuery selection, it retrieves only the HTML inside the first element in the matched set, along with any of its descendants.
 
For example, `$('ul').html();` will return this:
```
<li id="one"><em>fresh</em> figs</li>
<l i id="two">pine nuts</li>
<li id="three">honey</li>
<l i id="four">balsamic vinegar</l i>
```
Whereas `$('li').html();` will return this:
```
<em>fresh</em> figs
```
> Note how this returns only the content of the first
`<1i>` element. If you want to retrieve the value of every element.
you can use the `.each()` method.
 
## `.text()`
 
When this method is used to retrieve the text from a jQuery selection, it returns the content from every element in the jQuery selection, along with the text from any descendants.
 
For example, `$('ul').text();` will return this:
```
fresh figs
pine nuts
honey
balsamic vinegar
```
Whereas `$('li').text();` will return this:
```
fresh figspine nutshoneybalsamic vinegar
```
> Note: how this returns the text content of all `<1i>`
elements (including spaces between words), but
there are no spaces between the individual list items.
> 
> To get the content from `<input>` or `<textarea>`
elements, use the .val() method. 
> 
>For various examples of `.html()` and `.text()` see Duckett JavaScript and jQuery page 315.
---
| Method | Definition |
| --- | --- |
| `.html()` | This method gives every element in the matched set the same new content. The new content may include HTML. |
| `.text()` | This method gives every element in the matched set the same new text content. Any markup would be shown as text. |
| `.replaceWith()` | This method gives every element in the matched set the same new text content. Any markup would be shown as text. |
| `.remove()` | This method removes all of the elements in the matched set. |
---
## Changing Content
 
**When updating the content of an element, you can use a string, a variable, or a function.**
 
> When specifying new content, carefully choose when to use single quotes and when to use double quotes. If you append a new element that has·attributes, use single quotes to surround the content. Then use double quotes for the attribute values themselves. 
---
| Method | Definition |
| --- | --- |
| `.before()` | This method inserts content before the selected element(s) |
| `.after()` | This method inserts content after the selected element(s) |
| `.prepend()` | This method inserts content inside the selected element(s), after the opening tag. |
| `.append()` | This method inserts content inside the selected element(s), before the closing tag |
---
> There are also `.prependTo()` and `.appendTo()` methods. 
> 
>They work the other way around from `.prepend()` and `.append()`. So:
> 
>a. prepend (b) adds b to a
> 
>a.prependTo{b) adds a to b
> 
>a. append (b) adds b to a
> 
>a.appendTo(b) adds a to b 
> 
>***Additional examples Duckett JavaScript and jQuery page 319.***
 
## GETTING AND SETTING ATTRIBUTE VALUES 
---
| Method | Definition |
| --- | --- |
| `.attr()` | To get the value of an attribute, you specify the name of the attribute in the parentheses.  |
|  | To update the value of an attribute, you specify both the attribute name and its new value |
| `.removeAttr()` | This method removes a specified attribute (and its value). You just specify the name of the attribute that you want to remove from the element in the parentheses. |
| `.addClass()` | This method adds a new value to the existing value of the class attribute. It does not overwrite existing values.  |
| `.removeClass()` | This method removes a value from the cl ass attribute, leaving any other class names within that attribute intact. |
---
When the values of these attributes change, new CSS rules are applied to the elements, changing how they look. 
 
Using events to trigger changes to attribute values that apply new CSS rules is a popular way to make a web page interactive. 
 
>***Additional examples Duckett JavaScript and jQuery page 321.***
--- 
 
## GETTING & SETTING CSS PROPERTIES
 
**The `.css()` method lets you retrieve and set the values of CSS properties.**
 
To **get** the value of a CSS property, you indicate which property you want to retrieve in parentheses. If the matched set contains more than one element, it will return the value from the first element. 
 
To **set** the values of a CSS property, you specify the property name as the first argument in the parentheses, then a comma, followed by its value as the second argument. This will update every element in the matched set. You can also specify multiple properties in the same method using object literal notation
 
> Note: In the method used to set an individual property, the property name and its value are separated by a comma (because all parameters in a method are separated by a comma).
> 
>***Additional examples Duckett JavaScript and jQuery page 322.***
---
 
## Changing CSS Rules
 
```
$(function(){
    var backgroundColor = $('li').css('background-color');
    $('ul').append('<p>Color was: ' + backgroundColor + '</p>');
    $('li').css({
        'background-color': '#c5a996' ,
        'border': 'lpx solid #fff',
        'color': '#000',
        'font-family': 'Georgia',
        'padding-left': '+=75'
    } ) ;
} ) ; 
```
1. The backgroundColor variable is created. The jQuery selection contains all `<1i>` elements, and the `.css()` method returns the value of the background-color property of the first list item.
 
2. The background color of the first list item is written into the page using the `.append"()` method. Here, it is used to add content after the `<ul>`element.
 
3. The selector picks all `<li>` elements, and then the `.css()` method updates several properties at the same time:
 
- The background color is changed to brown
- A white border is added 
- The color of the text is changed to black
- The typeface is changed to Georgia
- Extra padding is added on the left 
 
> Note: It is better to change the value of a class attribute (to trigger new CSS rules in the style sheet) rather than to change CSS properties from within the JavaScript file itself. 
---
## WORKING WITH EACH ELEMENT IN A SELECTION 
 
| Method | Definition |
| --- | --- |
|`.each()` | Allows you to perform one or more statements on each of the items in the selection of elements that is returned by a selector - rather like a loop in JavaScript. |
|  | It takes one parameter: a function containing the statements you want to run on each element |
| `this` or `$(this)` | As the `.each()` method goes through the elements in a selection, you can access the current element using the `this` keyword. |
|  | You also often see `$(this)`, which uses the this keyword to create a new jQuery selection containing the current element. It allows you to use jQuery methods on the current element. |
---
 
## USING .EACH()
 
**The `.each()` method calls an anonymous function for each of the list items in the matched set.**
 
The `this` keyword refers to the current element node in the loop.
 
`$(this)` is used to create a jQuery object that contains the current element in the loop.
 
>***Additional examples Duckett JavaScript and jQuery page 325.***
 
## EVENT METHODS 
 
**The `.on()` method is used to handle all events**
 
```
$('li') .on('click', function() { 
    $(this) .addClass( ' complete');
} ) ; 
```
>1. The jQuery selection contains all of the <1 i >elements.
>2. The `.on()` method is used to handle events. It needs two parameters:
>3. The first parameter is the event you want to respond to. Here it is the
click event.
>4. The second parameter is the code you want to run when that event
occurs on any element in the matched set. This could be a named
function or an anonymous function. Above, it is an anonymous function
that adds a value of complete to the class attribute. 
---
| JQUERY EVENTS |  |
| --- | --- |
| UI |focus , blur, change |
| KEYBOARD | input, keydown, keyup, keypress |
| MOUSE | click, dblclick, mouseup, mousedown, |
|  | mouseover, mousemove, mouseout, hover |
| FORM | submit, select, change | 
| DOCUMENT | ready , load, unload | 
| BROWSER | error, resize , scroll | 
---
 
>***Additional examples Duckett JavaScript and jQuery page 326-327.***
---
 
## THE EVENT OBJECT 
 
---
| PROPERTY | DESCRIPTION| 
| --- | ---|
| type | Type of event, (e.g., click, mouseover)| 
| which | Button or key that was pressed| 
| data | An object literal containing extra information passed to the function when the event fires (See right-hand page for an example)| 
| target | DOM element that initiated the event| 
| pageX | Mouse position from left edge of viewport| 
| pageY | Mouse position from top of viewport| 
| timeStamp | Number of milliseconds from Jan 1st, 1970, to when the event was triggered (this is known as Unix Time). Does not work in Firefox.| 
---
| METHOD | DESCRIPTION| 
| --- | --- |
| `.preventdefault()` | Prevents the default (e.g., submitting a form)| 
| `.stopPropagation()` | Stops the event bubbling up to ancestors | 
---
 
>***Additional examples Duckett JavaScript and jQuery page 328-329.***
 
## ADDITIONAL PARAMETERS FOR EVENT HANDLERS
 
**The `.on()` method has two optional properties that let you:** 
- Filter the initial jQuery selection to respond to a subset of the elements; 
- Pass extra information into the event handler using object literal notation.
 
Example:
```
.on(events[, selector][, data], function(e));
```
>***Additional examples and explaination Duckett JavaScript and jQuery page 328-329.***
 
## DELEGATING EVENTS
 
```
$(function() {
    var listltem, itemStatus, eventType;
 
$( 'ul ').on(
    'click mouseover',
    ':not(#four)',
    {status: 'important'},
    function(e) {
        listltem = 'Item: ' + e.target.textContent + '<br />';
        itemStatus = 'Status: ' + e.data .status + ' <br />';
        eventType = 'Event : ' + e.type;
        $('#notes').html(listltem + itemStatus + eventType);
     }
  );
}); 
```
 
In this example, the event handler will run when users click or mouseover items in the list, except for the last list item. 
 
It writes out the content of the element the user interacted with, a status message (using the data property), and the event type.
 
The information passed in the data property here uses object literal notation (so it could handle multiple properties).
 
> 1. The event handler is triggered by click and mouseover events.
> 2. The selector parameter filters out the element whose id attribute has a value of four.
> 3. Additional data that will be used by the event handler is passed in as an object literal.
> 4. The event handler uses the event object to display the content of the element the user interacts with, the information from the data that was passed into the function, and the event type, under the list in a white box. 
 

# jQuery Pg. 354-357
 
## Ways to include jQuery in your page
 
**In addition to hosting the jQuery file with the rest of your website, you can also use a version that is hosted by other companies.**
> If you do this you should still include a fallback version 
 
**CDN** - (Content Delivery Network) - A series of servers spread out around the world. They are designed to serve static files very quickly.
 
## LOADING JQUERY FROM A CDN 
 
```
<script src=" //ajax .googl eapi s . com/ ajax/l i bs/ jquery / 1.10. 2/ jquery .min. js ">
</ script>
 
<script>
window .jQuery 11 document. write (' <script src=" j s/j query- 1.10. 2 .j s 11><\jscri pt> ' )
</script>
```
> It starts with a `<script>` tag that tries to load the jQuery file from the CDN. But note that the URL for the script starts with two forward slashes (not http:). This is known as a **protocol
relative URL**.
 
> If the user is looking at the current page through https, then they will not see an error that tells them there are unsecure items on the page. 
 
> This is often followed by a second `<script>` tag that contains a logical operator, which checks to see if jQuery has loaded. If it has not loaded, the browser tries to load the jQuery script from the same server as the rest of the website.
 
## WHERE TO PLACE YOUR SCRIPTS 
 
**The position of `<script>` elements can affect how quickly a web page seems to load.**
 
> `<script>` tags should go at the bottom of your HTML, before your closing `</body>` tag, so that the JavaScript does not try retrieve items before they are loaded.
 
# 6 Reasons for Pair Programming

## How does pair programming work?

**Driver** - the programmer who is typing and the only one whose hands are on the keyboard.

**Navigator** - uses their words to guide the Driver but does not provide any direct input to the computer.

## Why pair program?

Pair programming touches on all four skills of language development: 
- developers ***explain out loud*** what the code should do
- ***listen*** to others’ guidance
- ***read*** code that others have written
- ***write*** code themselves

### Greater efficiency

- In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.

- Research indicates that pair programing takes slightly longer, but produces higher-quality code, not as much time needed to troubleshoot and debug.

> - *When coming up with ideas and discussing solutions out loud, two programmers may come to a solution faster than one programmer on their own.*
> - Also, when the pair is stuck, both programmers can research the problem and reach a solution faster.

### Engaged collaboration

- The experience is more engaging and both programmers are more focused than if they were working alone.

- Harder to procrastinate or get off track when someone else is relying on you.

- Need to use the 15-minute rule less

- Boost confidence in students

### Learning from fellow students

- Working with a teammate can expose developers to techniques they otherwise would not have thought of.

> If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

- If one programmer is more experienced in a certain skill, they can teach a student who is less familiar with that area.

> Both developers gain from this interaction: one receiving the new information and the other speaking about the ideas and improving their communication skills and solidifying their understanding of the topic.

### Social skills

- Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills.

> When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself.

- This has long-term career impacts. As much as employers want strong programmers, they know it’s essential to hire people who can work well with others.

### Job interview readiness

- A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen.

> They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. 
> - *By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.*

### Work environment readiness

**Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product.**

> Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.