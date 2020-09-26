## Duckett HTML/CSS Chapter 7: Forms (144-175)
 
**HTML borrows the concept of a form to refer to different elements that allow you to collect information from visitors to your site.**
 
#### Forms
 
- Registering as a member of a website
- Signing up for newsletters or mailing lists
 
 
- #### Adding text

- **Text Input** - single-line
- **Password Input** - single-line; hidden text
- **Text Area** - multi-line
- Making Choices:
- **Radio Buttons** - Select only one option
- **Check Boxes** - Select and unselect miltiple options
- **Drop-Down Boxes** - Select one item out a list
- Submitting Forms:
- **Submit Buttons** - Submit information from form to another web page
- **Image Buttons** - Similar to submit button, but uses image for button
- Uploading Files:
- **File Upload** - Allows user to upload files/images to a website.
 
**Form prompts -- User fills out -- click submit -- server processes input information -- sends back a reponse to the user based on input**
 
A form may have several form controls, each gathering different information. The server needs to know which piece of inputted data corresponds with which form element.
 
Information is sent to the server as name/value pairs. (username-Nick, vote-yourmomlistenstonickleback)
  - If the form control allows the user to enter text, then the value of the form control is whatever the user has typed in. - **username-Nick**
  - If the form control allows you to choose from a fixed set of answers (e.g. radio buttons, checkboxes or a drop down list), the web page author will add code that gives each option an automatic value. - **vote-yourmomlistenstonickleback**
  - **You should never change the name of a form control in a page unless you know that the code on the server will understand this new value.**
 
Form Structure: **(pg 151)**
- **`<form>`** - This element should always carry the action attribute and will usually have a method and id attribute too.
- **`action`** - Its value is the URL for the page on the server that will receive the information in the form when it is submitted.
- **`method (get)`** - The values from the form are added to the end of the URL specified in the action attribute.
  - short forms (such as search boxes)
  - when you are just retrieving data from the web server (not sending information that should be added to or deleted from a database)
- **`method (post)`** - The values are sent in what are known as HTTP headers.
  - allows users to upload a file
  - is very long
  - contains sensitive data (e.g. passwords)
  - adds information to, or deletes information from, a database
- **`id`** - identify the form distinctly from other elements on the page
 
Elements:
- `<input>`
- `type="text"`
- `name`
- `size`
- `maxlength`
- `type="password"`
- `<textarea>`
- `type="radio"`
- `value`
- `checked`
- `type="checkbox"`
- `<option>`
- `multiple`
- `type="file"`
- `type="submit"`
- `type="image"`
- `<button>`
- `type="hidden"`
- `label`
- `for`
- `<fieldset>`
- `<legend>`
- `type="date"`
- `type="email"`
- `type="url"`
- `type="search"`
- `placeholder`
 
**Form Validation** - Validation helps ensure the user enters information in a form that the server will be able to understand when the form is submitted.
 
- Whenever you want to collectinformationfrom visitors you will need a form, which lives inside a <form> element.
- Information from a form is sent in name/value pairs.
- Each form control is given a name, and the text the user types in or the values of the options they select are sent to the server.
- HTML5 introduces new form elements which make it easier for visitors to fill in forms.
 
 
## Duckett HTML/CSS Chapter 14: Lists, Tables, and Forms (330-357)
 
 
**Unordered Lists**
- `none`
- `disc`
- `circle`
- `square`
 
**Ordered list**
- `decimal`
- `decimal-leading-zero`
- `lower-alpha`
- `upper-alpha`
- `lower-roman`
- `upper-roman`
 <br>
 <br>
 <br>
- **`list-style-image`**
- **`list-style-position`**
- **`outside`**
- **`inside`**
- **`list-style`**
- `width` - set the width of the table
- `padding` - set the space between the border of each table cell and its content
- `text-transform` - convert the content of the table headers to uppercase
- `letter-spacing`/`font-size` - add additional styling to the content of the table headers
- `border-top`/`border-bottom` - set borders above and below the table headers
- `text-align` - align the writing to the left of some table cells and to the right of the others
- `background-color` - change the background color of the alternating table rows
- `:hover` - highlight a table row when a user's mouse goes over it
- `tr.even` + `background-color` - Shade alternate rows
- `empty-cells`
  - `show`
  - `hide`
  - `inherit`
- `border-spacing`/`border-collapse`
  - `collapse`
  - `separate`
- `font-size` - sets the size of the text entered by the user.
- `color` - sets the text color
- `background-color` - sets the background color of the input.
- `border` - adds a border around the edge of the input box
- `border-radius` - can be used to create rounded corners (for browsers that support this property).
- `:focus` - pseudo-class is used to change the background color of the text input when it is being used.
- `:hover` - psuedo-class applies the same styles when the user hovers over them.
- `background-image` - adds a background image to the box.
 
 
- In addition to the CSS properties covered in other chapters which work with the contents of all elements, there are several others that are specifically used to control the appearance of lists, tables, and forms.

- List markers can be given different appearances using the list-style-type and list-style image properties.

- Table cells can have different borders and spacing in different browsers, but there are properties you can use to control them and make them more consistent.

- Forms are easier to use if the form controls are vertically aligned using CSS.

- Forms benefit from styles that make them feel more interactive.
 
## Duckett JS Chapter 6: Events (243-292)
 
 
#### Response Pathway:
 
- **Interactions create events**
- **Events trigger code**
- **Code responds to user**
 
 
**UI EVENTS** - Occur when a user interacts with the browser's user interface (UI) rather than the web page
 
- `load` - Web page has finished loading
- `unload` - Web page is unloading (usually because a new page was requested)
- `error` - Browser encounters a JavaScript error or an asset doesn't exist
- `resize` - Browser window has been resized
- `scroll` - User has scrolled up or down the page
 
**KEYBOARD EVENTS** - Occur when a user interacts with the keyboard (see also input event)
 
- `keydown` - User first presses a key (repeats while key is depressed)
- `keyup` - User releases a key
- `keypress` - Character is being inserted (repeats while key is depressed)
 
**MOUSE EVENTS** - Occur when a user interacts with a mouse. trackpad, or touchscreen
 
- `click` - User presses and releases a button over the same element
- `dbl click` - User presses and releases a button twice over the same element
- `mousedown` - User presses a mouse button while over an element
- `mouseup` - User releases a mouse button while over an element
- `mousemove` - User moves the mouse (not on a touchscreen)
- `mouseover` - User moves the mouse over an element (not on a touchscreen)
- `mouseout` - User moves the mouse off an element (not on a touchscreen)
 
#### How events are trigger javaScript code:
1. **Select the element node(s) you want the script to respond to.**
2. **Indicate which event on the selected node(s) will trigger the response.** Programmers call this `binding an event to a DOM node`.
3. **State the code you want to run when the event occurs.**
 
**Simplified**
- Select Element
- Specify Event
- Call Code
 
**Event handlers let you indicate which event you are waiting for on any particular element. There are three types of event handlers.**
 
- **HTML EVENT HANDLERS (pg 251) - *This is bad practice, but you need to be aware of it because you may see it in older code.***
- **TRADITIONAL DOM EVENT HANDLERS** (pg 252) - They are considered better than HTML event handlers because they let you separate the JavaScript from the HTML.
- **DOM LEVEL 2 EVENT LISTENERS** (pg 254) - Event listeners were introduced in an update to the DOM specification. They are now the favored way of handling events
 