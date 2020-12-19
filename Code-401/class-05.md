# Linked Lists


## What is a linked list?

Source: [Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

**A Linked List is a sequence of `Nodes` that are connected/linked to each other. The most defining feature of a Linked List is that each `Node` references the next `Node` in the link.**

Dictionary:

- **Linked List** - A data structure that contains nodes that links/points to the next node in the list.
- **Singly** - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
- **Doubly** - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
- **Node** - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
- **Next** - Each node contains a property called Next. This property contains the reference to the next node.
- **Head** - The Head is a reference type of type Node to the first node in a linked list.
- **Current** - The Current reference is a reference type of type Node that is currently being looked at. This node is traditionally used when traversing through a full linked list. When traversing, you typically reset the current to the head to guarantee you are starting from the beginning of the linked list.

## Traversal

`Next` must be used to traverse the `nodes` in the linked list. `Next` property is important because it will lead us where the next `node` is and allow us to extract the data appropriately.

> Note: you CAN NOT use a `foreach` or `for` loop when traversing the linked list.

The best way to approach a traversal is through the use of a `while()` loop. This allows us to continually check that the `Next` node in the list is not `null`. If we accidentally end up trying to traverse on a node that is null, a `NullReferenceException` gets thrown and our program will crash/end.

> The `Current` will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

## Big O
The Big O of time for `Includes` would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

The Big O of space for `Includes` would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.


## What’s a Linked List, Anyway? [Part 1]
Source: [What’s a Linked List, Anyway? [Part 1]](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

## Linear data structures


One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. 

We can think of a `linear data structure` like a game of hopscotch: in order to get to the end of the list, we have to go through all of the items in the list in order, or sequentially. Linear structures, however, are the opposite of non-linear structures. In `non-linear data structures`, items don’t have to be arranged in order, which means that we could traverse the data structure non-sequentially.

![Linear Linked List](https://miro.medium.com/max/700/1*Xokk6XOjWyIGCBujkJsCzQ.jpeg)

> When we use arrays in our code, we’re implementing a linear data structure! It can be helpful to think of arrays and linked lists as being similar in the way that we sequence data. In both of these structures, ***order matters***.


## Memory management

When an `array` is created, it needs a certain amount of memory. If we had 7 letters that we needed to store in an array, we would need 7 bytes of memory to represent that array. But, we’d need all of that memory in one contiguous block. That is to say, our computer would need to locate 7 bytes of memory that was free, one byte next to the another, all together, in one place.

On the other hand, when a `linked list` is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.

![Memory Allocation Example](https://miro.medium.com/max/700/1*G43FVT5xJ1n1QDKVNZUxXQ.jpeg)

- **Static Data Structures** - needs all of its resources to be allocated when the structure is created.

- **Dynamic Data Structures** - can shrink and grow in memory. It doesn’t need a set amount of memory to be allocated in order to exist, and its size and shape can change, and the amount of memory it needs can change as well.

## Parts of a linked list

The starting point of the list is a reference to the first node, which is referred to as the `head`. Nearly all linked lists must have a `head`, because this is effectively the only entry point to the list and all of its elements, and without it, you wouldn’t know where to start! The end of the list isn’t a node, but rather a node that points to `null`, or an empty value.

![Parts of a Linked List Example](https://miro.medium.com/max/700/1*K0_eV07tJtKQSVGKfP18bw.jpeg)

## Lists for all shapes and sizes

- Singly linked lists are the simplest type of linked list, based solely on the fact that they only go in one direction. 
    - There is a single track that we can traverse the list in; we start at the `head` node, and traverse from the `root` until the last `node`, which will end at an empty `null` value.

- Doubly linked list, there are two references contained within each node: a reference to the next node, as well as the previous node. 
    - This can be helpful if we wanted to be able to traverse our data structure not just in a single track or direction, but also backwards, too.
    
![Sinlgy vs. Doubly vs. Circular Linked lists](https://miro.medium.com/max/700/1*AeMDLFUjR0w0J4n8CP4H6g.jpeg)

> **Circular linked list** - it has a node that acts as the tail of the list (rather than the conventional head node), and the node after the tail node is the beginning of the list.

Resources
If you think linked lists are super cool, check out these helpful resources.

- [Differences between Arrays and Linked Lists, Damien Wintour](http://www.necessaryandsufficient.net/2008/05/differences-between-arrays-and-linked-lists/)

- [Data Structures: Arrays vs Linked Lists, mycodeschool](https://www.youtube.com/watch?v=lC-yYCOnN8Q)

- [Linked Lists: The Basics, Dr. Edward Gehringer](https://people.engr.ncsu.edu/efg/210/s99/Notes/LinkedList.1.html)

- [Introduction to Linked Lists, Dr. Victor Adamchik](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked%20Lists/linked%20lists.html)

- [Data Structures & Implementations, Dr. Jennifer Welch](http://faculty.cs.tamu.edu/welch/teaching/211.s03/lnotes1.pdf)

- [Static Data Structures vs. Dynamic Data Structures, Ayoma Gayan Wijethunga](http://www.ayomaonline.com/academic/static-vs-dynamic-data-structures/)

## What’s a Linked List, Anyway? [Part 2]
Source: [What’s a Linked List, Anyway? [Part 2]](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)
