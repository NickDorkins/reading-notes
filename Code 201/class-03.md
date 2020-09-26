## Duckett HTML Chapter 3: Lists

**Ordered Lists** are lists where each item in the list is numbered.
  - Created with `<ol>` element

**Unordered Lists** are lists that begin with a bullet point.
- Created with `<ul>` element

**Definition Lists** are made up of a set of terms along with the definitions for each of those terms.

**Nested Lists** (Listception) are lists that are created inside another list.

#### Elements:
- **`<ol>`** = Ordered List
- **`<ul>`** = Unordered List
- **`<li>`** = List Item
- **`<dl>`** = Definition List 
- **`<dt>`** = Definition Term (Word/s you are defining)
- **`<dd>`** = Different Definitions (for the same term)

## Duckett HTML Chapter 13: Boxes

You can set several properties that affect the appearance of these boxes. 
- Control the dimensions of boxes
- Create borders around boxes
- Set margins and padding for boxes
- Show and hide boxes

Designers have recently started to use percentages and ems more for measurements as they try to create designs that are flexible across devices which have different-sized screens.


#### Properties:
- **width** = left to right dimensions
- **height** = top to bottom dimensions
  *  Can set them using either px count, percentage of browser window or box containing them, or ems (size of the box is based on the size of text within it)  
- **min-width/min-height** = specifies the smallest size a box can be displayed at when the browser window is narrow/short
- **max-width/max-height** = indicates the maximum width/height a box can stretch to when the browser window is wide/tall
- **overflow** = tells the browser what to do if the content contained within a box is larger than the box itself. It can have one of two values:
  - **hidden** = hides any extra content that does not fit in the box
  - **scroll** = adds a scrollbar to the box so that users can scroll to see the missing content

Every box has three available properties that can be adjusted to control its appearance:

- **Boarder** = separates the edge of one box from another
- **Margin** = sit outside the edge
of the border
- **Padding** = pace between the border of a box and any content contained within it

## Duckett JS Chapter 4: Decisions and Loops

if else statement checks a condition
* If it resolves to ***true*** the first block is executed
* If the condition resolves to ***false*** the second code block is run instead

Switch statements start with variable called **"switch value"**

Each case indicates a possible value for this variable and the code should run if the variable matches that value.

switch (level) {
  
  case 'One':
    title = 'Level 1';
    break;

  case 'Two':
    title = 'Level 2';
    break;

 case 'Three':
    title = 'Level 3';
    break;

  default:
  title = 'Test";
  break;   
}

#### IF...ELSE
* if else = no need to provide an ***else*** option
* with a series of ***if*** statements they are checked even if a match is found 
* performs slower than ***switch*** statements

#### SWITCH
* default option = runs if none of the cases match
* match found = runs code block
* break = stops rest of the ***switch*** statements from running
* performs faster than several ***if*** statements

#### LOOPS
* for = runs code block a specific numer of times
* while = continues to loop as long as the condition is ***true***
* do while = similar to a ***while*** loop; however if will always run at least once, even if the condition evaluates ***false***
**initialization | condition | update**
---------------- | --------- | --------
var i = 0; | i < 10; | i++        
created first time loop is run | loop will continue to run until this condition is met | incriment operator

***Conditional Statements* = code makes decisions about what to do next**

***Comparison Operators* (===, !==, ==, !=, <, >, <=, =>) = compare operands**

***Logical Operators* = allow developer to combine more than one set of comparison operators**

***if else statements* = run one set of code; one condition for ***true***; another condition for ***false*****

***Switch Statements* = compare values against possible outcomes; default operator if none match**

**Data types can be coerced from one type to another**

**All values evaluate to either *truthy* or *falsy***

***3 types of loops: for, while, do while* = each repeats a set of statements**










