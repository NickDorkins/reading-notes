## Duckett HTML Chapter 6: Tables (pp.126-145)

When representing information in a table, you need to think in terms of a grid made up of rows and columns like a spreadsheet.


- Use the four key elements for creating tables
- Represent complex data using tables
- Add captions to tables

-`<table>` -  element used to create a table. 
  - The contents of the table are written out row by row.

-`<tr>` - indicates the start of each row by the opening`<tr>` tag.
  - The tr stands for table row.
  - `<tr>` is followed by one or more `<td>` elements (one for each cell in that row).
At the end of the row you use a closing `</tr>` tag.
`<td>`
Each cell of a table is represented using a`<td>` element. (The td stands for table data.)
At the end of each cell you use a closing `</td>` tag.

-`<th>` - Table Heading
- rowspan - can be used on a`<th>` or`<td>` element to indicate how many rows a cell should span down the table.

-`<thead>` - headings of the table should sit inside the`<thead>` element.
-`<tbody>` - body should sit inside the`<tbody>` element.
-`<tfoot>` - footer belongs inside the`<tfoot>` element.
`<!-- end pg 145 -->
## Duckett JS Chapter 3: Functions, Methods, and Objects (pp.106-144)

### CREATE THE OBJECT, THEN ADD PROPERTIES & METHODS:

- Once you have created an object, the syntax for adding or removing any properties and methods from that object is the same.

**Example:**
LITERAL NOTATION var hotel = {}
hotel .name= 'Quay';
hotel .rooms = 40;
hotel.booked = 25; hotel.checkAvailabil ity =function()
return this.rooms - this.booked;
};

- A colon separates the key/value pairs.There is a comma between each key/value pair.

**Example:**
OBJECT CONSTRUCTOR NOT A TION var hotel = new Object();
hotel.name = ' Quay';
hotel .rooms = 40;
hotel . booked= 25; hotel.checkAvailability =function()
return this.rooms - this.booked;
};

- The function can be used to create multiple objects. The this keyword is used instead of the object name.

### CREATING AN OBJECT WITH PROPERTIES & METHODS

#### You can combine arrays and objects to create complex data structures: **Arrays** can store a series of objects and remember their order. **Objects**can hold arrays as values of their properties.

DOM is needed to access and update the contents of a webpage.

DOM creates a model of the current webpage.

**Global Variables** - are not part of the object but can be called into an object

- Functions allow you to group a set of related statements together that represent a single task.

- Functions can take parameters, information required to do their job and may return a value.

- An object is a series of variables and functions that represent something from the world around you.

- In an object, variables are known as properties of the object; functions are known as methods of the object.

- Web browsers implement objects that represent both the browser window and the document loaded into the browser window.

- JavaScript also has several built-in objects such as String, Number, Math, and Date. Their properties and methods offer functionality that help you write scripts.

- Arrays and objects can be used to create complex data sets and both can contain the other.