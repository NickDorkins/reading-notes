# Read: 09 - Refactoring

## Concepts of Functional Programming in Javascript
Source: [Medium.com](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

> “Complexity is anything that makes software hard to understand or to modify." — John Outerhout

- **Immutability** - unchanging over time or unable to be changed.

- **Pure function** - A function that has the following properties: 
  - Its return value is the same for the same arguments. 
  - It does not cause any observable side effects
  
Thus a pure function is a computational analogue of a mathematical function

---

## What is Functional Progamming?

> Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia

:thought_balloon: :question: Literal Language?  :question: :thought_balloon:

### Impure Function:
```
let PI = 3.14;

const calculateArea = (radius) => radius * radius * PI;

calculateArea(10); // returns 314.0
```

### Pure Function
```
let PI = 3.14;

const calculateArea = (radius, pi) => radius * radius * pi;

calculateArea(10, PI); // returns 314.0
```
> Is lower case `pi` on line 3 = `potato`?


### Reading Files
*If our function reads external files, it’s not a pure function — the file’s contents can change.*

### Random number generation
*Any function that relies on a random number generator cannot be pure.*

### It does not cause any observable side effects
Examples of observable side effects include modifying a global object or a parameter passed by reference.

<br><br>

## * * * Mutability is discouraged in functional programming. * * * 

## * * * Pure functions are stable, consistent, and predictable. * * *

> ####### Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.

<br><br>

### Pure functions benefits

The code’s definitely easier to test. No need to mock anything. So you can unit test pure functions with different contexts:

- Parameter = A → Expected return value = B
- Parameter = C → Expected return value = D

---

## Immutability

***Unchanging over time or unable to be changed.***

- Recursion - occurs when a thing is defined in terms of *itself* or of *its type*. Recursion is used in a variety of disciplines ranging from linguistics to logic. The most common application of recursion is in mathematics and computer science, where a function being defined is applied within its own definition.   ~~~ Wikipedia 


- Slug/Slugify - human-readable, unique identifier, used to identify a resource instead of a less human-readable identifier like an id . You use a slug when you want to refer to an item while preserving the ability to see, at a glance, what the item is. ~~~ [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Glossary/Slug#:~:text=A%20Slug%20is%20the%20unique,page's%20slug%20is%20Glossary%2FSlug%20.)

> ##### "The origin of the term slug derives from the days of hot-metal printing, when printers set type by hand in a small form called a stick. Later huge Linotype machines turned molten lead into casts of letters, lines, sentences and paragraphs. A line of lead in both eras was known as a slug."

Slug/Slugify Example:
- `toLowerCase`: converts the string to all lower case
- `trim`: removes whitespace from both ends of a string
- `split` and `join`: replaces all instances of match with replacement in a given string

We combine all these 4 functions and we can "`slugify`" our string.

---

### Referential transparency

- `square function` - variabe * variable

> This is pure becuse it will always have the same output, given the same input.

### * * * If a function consistently yields the same result for the same input, it is **referentially transparent**. * * *

---

### Functions as first-class entities

Functions as first-class entities can:
- refer to it from constants and variables
- pass it as a parameter to other functions
- return it as result from other functions

### Higher-order functions

When we talk about higher-order functions, it means that a function either:
- takes one or more functions as arguments, or
- returns a function as its result

### Filter

- Filter Function - expects a `true` or `false` value to determine if the element should or should not be included in the result collection.

---

## Refactoring JavaScript for Performance and Readability
Source: [dev.to](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec)

Tools: [Solving Puzzles With High-Performance JavaScript](https://dev.to/healeycodes/solving-puzzles-with-high-performance-javascript-3o4k)

> *There's a middle ground between speed and comprehension and that's where good code lives.* ~~~ Andrew Healey

- **URL-shortening** - accepts a long URL and returns a short URL that forwards visitors to the long URL.

- **Hash function** - used to map a given key to a location in the hash table.

- **`friendly-words`** - Random legible word to return on URL instead of the ball of chaos you would normally see, these are pulled from curated files.

| Type | Definition |
| --- | --- |
| words/objects.txt | The direct object receives the action of the sentence. The direct object is usually a noun or pronoun. |
| words/predicates.txt |The predicate expresses action or being within the sentence. The simple predicate contains the verb and can also contain modifying words, phrases, or clauses. |
| words/teams.txt | This is a list of synonyms for "team". They're a special subset of objects. |
| words/collections.txt |This is a list of synonyms for "collection". |














