## Chapter 3: Object Literals (pp.100-105)
 
- If a variable is part of an object, it is called a **property**.
  - Properties tell us about the object.
- If a function is part of an object, it is called a **method**.
  - Method represents tasks that are associated with the object.
Like variables and named functions, properties and methods have a name and a value. In an object, that name is called a **key**.
An object **CANNOT** have **2 KEYS** of the same name. Keys are used to access their corresponding values.
The value of a property can be a string, number, Boolean, array, or even another object. The value of a method is always a function.
 
var hotel = {
name: 'Quay', **STRING**                               -|
rooms: 40,    **NUMBER**                                |
booked: 25,   **NUMBER**                                |
gym: true,    **BOOLEAN**                               | **OBJECT**
roomTypes: ['twin', 'double', 'suite'], **ARRAY**       |
checkAvailability: function() {       **FUNCTION**      |
 return this.rooms - this.booked;                       |
  }                                                    -|
}
 
 
 
Programmers use a lot of name/value pairs:
- HTML uses attribute names and values.
- CSS uses property names and values.
 
In JavaScript:
- Variables have a name and you can assign them a value of a string, number, or Boolean.
- Arrays have a name and a group of values. (Each item in an array is a name/value pair because it has an index number and a value.)
- Named functions have a name and value that is a set of statements to run if the function is called.
- Objects consist of a set of name/value pairs (but the names are referred to as keys)
 
The object is the curly braces and their contents. **{}**
The object is stored in a variable called **hotel**, so you would refer to it as the **hotel object**.
 
Each **key** is separated from it's value by a colon.(:)
Each **property value** is seaparated from it's method with a comma (,).
- You do not follow the same logic for the last value.
 
Use dot notation to access properties or methods.
- You may also use square brackets
 
var hotelName = hotel.name; **DOT NOTATION**
var hotelName = hotel['name']; **SQUARE BRACKETS**
 
**DOT NOTATION**- Access property or method
**SQUARE BRACKETS**-Can access property, but **not the method**
 
## Chapter 5: “Document Object Model” (pp.183-242)
 
**The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.**
 
The DOM is neither part of HTML, nor JavaScript; it has a separate set of rules and covers 2 primary areas:
 
**MAKING A MODEL OF THE HTML PAGE**
- When the browser loads a web page, it creates a model of the page in memory.
- The DOM specifies the way in which the browser should structure this model using a DOM tree.
- The DOM is called an object model because the model (the DOM tree) is made of objects.
- Each object represents a different part of the page loaded in the browser window.
 
 
 
**ACCESSING AND CHANGING THE HTML PAGE**
The DOM also defines methods and properties to access and update each object in this model, which in turn updates what the user sees in the browser.
 
You will hear people call the DOM an **Application Programming Interface (API)**. User interfaces let humans interact with programs; APls let programs (and scripts) talk to each other. The DOM states what your script can "ask the browser about the current page, and how to tell the browser to update what is being shown to the user
 
 
BODY OF HTML PAGE
<html>
  <body>
    <div id="page">
      <h1 id="header">List</h1>
      <h2>Buy groceries</h2>
      <ul>
        <li id="one" class="hot"><em>fresh</em> figs</li>
        <li id="two" class="hot">pine nuts</l i>
        <li id="three" class="hot">honey</li>
        <li id="four">balsamic vinegar</l i>
      </ul>
      <script src="js/l i st.js"></script>
    </div>
  </body>
</html >
 
**Reference page 187**
 
- At the top of the tree a document node is added; it represents the entire page.
- HTML elements describe the structure of an HTML page.
- The opening tags of HTML elements can carry attributes and these are represented by attribute nodes in the DOM tree.
- Attribute nodes are not children of the element thar carries them; they are part of that element. Once you access an element, there are specific JavaScript methods and properties to read or change that element's attributes. For example, it is common to change the values of cl ass attributes to trigger new CSS rules that affect their presentation.
- Once you have accessed an element node, you can then reach the text within that element. This is stored in its own text node.
- Text nodes cannot have children. If an element contains text and another child element, the child element is not a child of the text node but rather a child of the containing element. This illustrates how the text node is always a new branch of the DOM tree, and no further branches come off of it.
 
 
**Accessing and updating the DOM tree involves two steps:**
1: Locate the node that represents the element you want to work with.
2: Use its text content, child elements, and attributes.
 
 
**STEP 1: ACCESS THE ELEMENTS**
 
SELECT AN INDIVIDUAL ELEMENT NODE:
- **getElementByld()** - Uses the value of an element's id attribute, all id's should be unique.
- **querySe1ector()** - Uses a CSS selector, and returns the first matching element.
- Select individual elements by traversing from one element to another within the DOM tree.
 
SELECT MULTIPLE ELEMENTS (NODELISTS):
 
- **getElementsByClassName()** - Selects all elements that have a specific value for their class attribute.
- **getElementsByTagName()** - Selects all elements that have the specified tag name.
- **querySelectorAll()** - Uses a CSS selector to select all matching elements.
 
TRAVERSING BETWEEN ELEMENT NODE:
 
- parentNode - Selects the parent of the current element node this will return just one element.
- previousSibling/nextSibling - Selects the previous or next sibling from the DOM tree.
- firstChild/lastChild - Select the first or last child of the current element.
 
**STEP 2: WORK WITH THOSE ELEMENTS**
 
ACCESS/UPDATE TEXT NODES:
 
- The text inside any element is stored inside a text node.
- nodeValue - Lets you access or update contents of a text node.
- The text node does not include text inside any child elements.
 
WORK WITH HTML CONTENT:
 
- innerHTML - property allows access to child elements and text content.
- textContent - Allows access to only the text content of the element.
- createElement()/createTextNode()/appendChild()/removeChild() - Allows you create new nodes, add nodes to a tree, and remove nodes from a tree.
  - This is called DOM manipulation
 
ACCESS OR UPDATE ATTRIBUTE VALUES:
 
- className/id - Lets you get or update the value of the class and id attributes.
- hasAttribute() - checks if an attribute exists.
- getAttribute() - gets the value, if shown to exist.
- setAttribute() - Updates the value.
- removeAttribute() - Removes an attribute.
 
**The terms elements and element nodes are used interchangeably but when people say the DOM is working with an element, it is actually working with a node that represents that element.**
 
**Methods that find elements in the DOM tree are called DOM queries.**
  - When you need to work with an element more than once you should use a variable to store the results of this query.
 
**When a script selects an element to access or update, the interpreter must find the element(s) in the DOM tree.**
  - **Once it has found the node that represents the element(s), you can work with that node, it's parent, or any children.
 
**When people talk about storing elements in variables, they are really storing the location of the element(s) within the DOM tree in a variable.
- The properties and methods of that element node work on the variable.
- If your script needs to use the same element(s) more than once, you can store the location of the element(s) in a variable.
- This saves the browser time looking through the DOM tree to find the same element(s) again.
  - This is known as **caching the selection**.
- People may also be refer to this as: the variable stores a reference to the object in the DOM tree.
 
getElementById()/querySelector() - Can search an entire document and return individual elements. Both use similar syntax.
- getElementById() - Most efficient way to return an element because you will only have one id for the attribute.
- querySelector() - Parameter is a CSS selector, can accurately target many more elements.
 
**SELECTING AN ELEMENT FROM A NODELIST**
 
There are two ways to select an element from a Nodelist:
The **item()** method and **array syntax**.
Both require the index number of the element you want.
 
**THE item() METHOD**
 
Nodelists have a method called **item()** which will return an individual node from the Node list.
 
You specify the index number of the element you want as a parameter of the method inside the parentheses.
 
Executing code when there are no elements to work with wastes resource.
- check that there is at least one item in the Nodelist before running any code
- use the **length** property of the Nodelist
 
Reference page 198
1. Select elements that have a class attribute whose value is **hot** and store the Nodelist in a variable called **e1ements**.
2. Use the **1ength** property to check how many elements were found. If one or more are found, run the code in the if statement.
3. Store the first element from the Node List in a variable called **firstitem**
 
**ARRAY SYNTAX**
 
Array syntax is preferred over the item() method because it is faster.
Before selecting a node from a NodeList, check that it contains nodes.
If you repeatedly use the NodeList, store it in a variable.
 
You can access individual nodes using square bracket syntax similar to that used to access individual items in an array.
 
You specify the index number of the element you want inside square brackets that follow the NodeList.
 
**REPEATING ACTIONS FOR AN ENTIRE NODELIST**
 
When you have a NodeList, you can loop through each node in the collection and apply the same statements in each.
 
Refernce page 204
- Once the NodeList has been created, a **for  loop** is used to go through each element in the NodeList.
- All of the statements inside the **for loop's** curly braces are applied to each element in the NodeList one-by-one.
- To indicate which item of the NodeList is being worked with, the counter **i** is used in the array style syntax.
 
**TRAVERSING THE DOM**
 
When you have an element node, you can select another element in relation to it using these five properties. This is known as traversing the DOM.
 
**parentNode** - Finds the element node for the containing (or parent) element in the HTML.
**previousSibling/nextSibling** - Finds the previous or next sibling of a node if there are siblings.
**firstChild/lastChild** - Finds the first or last child of the current element.
 
These are properties of the current node (not methods to select an element); therefore, they do not end in parentheses.
 
If you use these properties and they do not have a previous/next sibling, or a first/last child, the result will be null.
 
These properties are read-only; they can only be used to select a new node, not to update a parent, sibling, or child.