## Read: 04 - HTML Links, CSS Layout, JS Functions

### Duckett HTML Chapter 4: Links (74-93)

##### **Common Links:**

- Links from one website to another
- Links from one page to another on the same website
- Links from one part of a web page to another part of the same page
- Links that open in a new browser window
- Links that start up your email program and address a new email to someone

**Links are created using the <a> element. Users can click on anything between the opening <a> tag and the closing </a> tag. You specify which page you want to link to using the href attribute**

**Anthing between your opening and closing <a> tags is known as LINK TEXT.**

Example: `<a href="http://www.google.com>Search Here</a>`
- **Search Here** = LINK TEXT

**Ensure that all of your link text is obvious and clear**
  - Think of what people may be looking for and name your links accordingly.
  - Try to be specific, vague links may get missed.
 - `<a>` = Anchor Tag, needed to add a link to your page.
 - href = attribute that tells your link text to follow the web address.
 - URL = Uniform Resource Locator
 - Absolute URL = Goes to a specific page on a website, if not used it will display the homepage.
 Relative URL = Links pages within the same webite. Shorthand versions of absolute URL's.

**Root folder** contains: A file called index.html which is the homepage for the entire site

**Sub-directory** contains: A file called index.html which is the homepage for that section

**Relative URL's** are quicker because you don't need to repeat the domain name in each link.

If all of the files in your site are in one folder, you simply use the file name for that page.

**mailto** starts users set default email program and addresses an email to a specific email address.
- Example: `<a href="mailto:johnwick@gmail.com">John Wick</a>`

**target** = if you want the link to open in a new window or tab, the value of this attribute should be "_blank". (Best practice to warn user that the link will open a new window.)

**#+id** = this will return the user to the location that this ID is use in the webpage. i.e. if you have an id tag at the top of the page named id="top" and you write `<a href="#top">Return to top</a>` this will return the user to the top of the page.
  - Similarly you can link the user to a separate page of your site and a specific id tag. **`<a href="URL/file/file/file/#id"></a>`**


### Duckett HTML Chapter 15: Layout (358-404)

**CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.**

**Block Level Boxes** = start on new line and are the main building blocks of the layout.

**Inline Boxes** = Can float and flow between surrounding text.

#### Additional attributes for these elements:
- width
- sometimes height
- boarders
- padding
- margins
- background colors

**If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.**

You can group a number of elements within a box using a **`<div>`** tag

#### Controlling the position of elements:
**Normal Flow**
- Every new element starts on a new line
- Stacks content and moves down the page
- Even if you specify the width of the boxes and there is space for two elements to sit side-byside, they will not appear next to each other.

**Relative Positioning**
- shift element to top, left, right, or bottom of wherever it would have been placed.
- Does not affect surrounding elements; they stay in the position they be in for normal flow.

**Absolute Positioning**
- positions element in relaton to its containing element
- taken out of normal flow, other elements ignore the space occupied by this element.
- Absolutely positioned elements move as users scroll up and down the page.

**Fixed Positioning**
- form of absolute positioning 
- positions the element in relation to the browser window, as opposed to the containing element.
- Do now affect surrounding elements
- Do not move when user scrolls

**Floating Elements**
- takes element out of normal flow
- positions far left or right of containing box
- becomes a block-level element around which other content can flow

**When you move any element from normal flow, boxes can overlap. The z-index property allows you to control which box appears on top.**

The size of a user's screen affects how big they can open their windows and how much of the page they will see

The higher the resolution, the smaller the text appears. Many mobile devices have screens that are higher resolution than their desktop counterparts.

**Fixed width layout** designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.

**Advantages**
- Pixel values are accurate at controlling size and positioning of elements.
- The designer has far greater control over the appearance and position of items on the page than with liquid layouts.
- You can control the lengths of lines of text regardless of the size of the user's window.
- The size of an image will always remain the same relative to the rest of the page.

**Disadvantages**
- You can end up with big gaps around the edge of a page.
- If the user's screen is a much higher resolution than the designer's screen, the page can look smaller and text can be harder to read.
- If a user increases font sizes, text might not fit into the allotted spaces.
- The design works best on devices that have a site or resolution similar to that of desktop or laptop computers.
- The page will often take up more vertical space than a liquid layout with the same content.

**Liquid layout designs** stretch and contract as the user increases or decreases the
size of their browser window. They tend to use percentages.

**Advantages**
- Pages expand to fill the entire browser window so there are no spaces around the page on a large screen.
- If the user has a small window, the page can contract to fit it without the user having to scroll to the side.
- The design is tolerant of users setting font sizes larger than the designer intended (because the page can stretch).

**Disadvantages**
- If you do not control the width of sections of the page then the design can look very different than you intended, with unexpected gaps around certain elements or items squashed together.
- If the user has a wide window, lines of text can become very long, which makes them harder to read.
- If the user has a very narrow window, words may be squashed and you can end up with few words on each line.
- If a fixed width item (such as an image) is in a box that is too small to hold it (because the user has made the window smaller) the image can overflow over the text
 
- <div> elements are often used as containing elements to group together sections of a page.
- Browsers display pages in normal flow unless you specify relative, absolute, or fixed positioning.
- The float property moves content to the left or right of the page and can be used to create multi-column layouts. (Floated items require a defined width.)
- Pages can be fixed width or liquid (stretchy) layouts.
- Designers keep pages within 960-1000 pixels wide, and indicate what the site is about within the top 600 pixels (to demonstrate its relevance without scrolling).
- Grids help create professional and flexible designs. 
- CSS Frameworks provide rules for common tasks. 
- You can include multiple CSS files in one page.



### Duckett JS Chapter3: Functions Methods and Objects (86-99)

- **Function Keyword**
  - only contains one statement
  - store the instructions for that specific task
- **Function Name**
  - Calls the function
- **Code Block**
  - function executes the code in the code block
- **Parameters**
  - Function similar to variables


### 6 Resaons for Pair Programming

#### Benefits of Pair Programming
- **Greater Efficiency**
  - Catch mistakes while building
  - Takes slightly longer
  - Better quality code
  - Less troubleshooting/debugging

- **Engaged Collaboration**
  - more engaging 
  - more focused than if they were working alone
  - learning to know when to ask for help
  - stick to the 15 minute rule
  - often find a solution together without needing to ask for additional help
  
- **Learning from fellow students**
  - expose developers to techniques they otherwise would not have thought of
  - If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.
  - programmers well versed in a specific skill can teach a student who is less familiar with that area3
  - less experienced programmer learns and develops new skill

- **Social skills**
  - communication is key
  - develop interpersonal skills
  - long-term career impacts
  - Employers want strong programmers and people that work well with others

- **Job Interview Readiness**
  - common step = pair programming between a current employee and an applicant
  - code challenges
  - build project of feature
  - debugging
  - get a feel for your workstyle
  - work well with others
  - good communication skills

- **Work Environment Readiness**

**Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.**