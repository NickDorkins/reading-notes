## Duckett HTML Chapter 2: Text

#### When creating a web page, you add tags (known as markup) to the contents of the page. These tags provide extra meaning and allow browsers to show users the appropriate structure for the page.

- **Structural markup:** the elements that you can use to describe both headings and paragraphs.

- **Semantic markup:** which provides extra information; such as where emphasis is placed in a sentence, that something you have written is a quotation (and who said it), the meaning of acronyms, and so on.

**HTML has six "levels" of headings:** h1 being the largest and h6 being the smallest.

- Each browser displays headings differently, if you have trouble getting the correct size, utilize CSS to get the appropriate size for the content that you are creating.

- **`<p>`** = paragraphs

- **`<b>`** = bold

- **`<i>`** = italic

- **`<sup>`** = superscript ( Example: the small "th" to the top right if you were to write 4th)

- **`<sub>`** = subscript (Example: characters that fall below the normal line of text such as chemical formulations. It would be the "2" in H2O)

- **White space** = additional spacing intentionally put into lines of code to make it easier to read/follow. However when rendered the white space will be gone, this is known as **white space collapsing**.

- **`<br>`** = Line breaks - even when written inline it will push the following text to the next line on the rendered page.

- **`<hr>`** = horizontal rule - creates a solid line across the page creating a separation between content.

- **`<strong>`** =indicates that its content has strong importance.

- **`<em>`** = lement indicates emphasis that subtly changes the meaning of a sentence.


## Chapter 10: Ch.10 Introducing CSS

The key to understanding how CSS works is to imagine that there is an invisible box around every HTML element.

Block level elements look like they start on a new line. - Example: `<h1>- <h6>, <p> and <div>`

Inline elements flow within the text and do not start on a new line. Example: `<b>, <i>, <img>, <em> and <span>`

- **Selectors** indicate which element the rule applies to. The same rule can apply to more than one element if you separate the element names with commas.
- **Declarations** indicate how
the elements referred to in the selector should be styled. Declarations are split into two parts (a property and a value), and are separated by a colon.
- **Properties** indicate the aspects of the element you want to change. For example, color, font, width, height and border.
- **Values** specify the settings
you want to use for the chosen properties. For example, if you want to specify a color property then the value is the color you want the text in these elements to be.

## Chapter 2: Basic JavaScript Instructions

- **var** = keyword ( if a variable name is more than 2 words, use camelCase)
- In order to use the variable you **MUST** first name it, AKA identifier.
- **(=)** = assignment operator
- **Variable value** = output based on the input identifier.

**Until you have assigned a value to the variable, it is known as *"unidentified"***

## Chapter 4: Decisions and Loops

- **== - equal to** = This operator compares two values to see if they are the same.

- **!= - is not equal to** = This operator compares two values to see if they are not the same.

- **=== - strict equal to** = This operator compares two values to check that both the data type and value are the same.


- **!== - strict is not equal to** = This operator compares two values to check that both the data type and value are not the same.

- **(>) Greater than** = This operator checks if the number on the left is greater than the number on the right.

- **(<) Less than** = This operator checks if the number on the left is less than the number on the right.

- **(>=) Greater than or Equal to** = This operator checks if the number on the left is greater than or equal to the number on the right.

- **(<=) Less than or Equal to** = This operator checks if the number on the left is less than or equal to the number on the right.

- **Operand** = Placed on each side or the operator, can be variables or values. Often enclosed in brackets.    


- **(score >= pass)**
    - () = enclosing brackets
    - score/pass = operand
    - >= = comparison Operator

- **(&&) Logical And** = Tests more than one condition.

- **(||) Logical Or** = Tests at least one condition.

- **(!) Logical Not** = Takes a single Boolean value and inverts it.