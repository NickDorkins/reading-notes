# Class-02: Testing and Modules

Source: [In Tests We Trust — TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)


Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.

But **Test-Driven Development** is a strategy to think (and write!) tests first.

If you know what your expected output is you can write a test to ensure that you are receiving the correct end ersult prior to writing any functional code.

```
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
```

Symantic naming is important, it allows you or another dev to return to this code later and know exactly what the test is expecting.

Other thing to care about is the structure. A convention widely used is the AAA: **Arrange**, **Act** and **Assert**.

- Arrange: you need to organize the data needed to execute that piece of code (input);

- Act: here you will execute the code being tested (exercise the behaviour);

- Assert: after executing the code, you will check if the result (output) is the same as you were expecting.


## The Cycle

I hope at this time you didn’t give up of this text because this is an example of an important thing about TDD: the cycle.

The cycle is made by three steps:

🆘 Write a unit test and make it fail 
> it needs to fail because the feature isn’t there

✅ Write the feature and make the test pass! 

🔵 Refactor the code — the first version doesn’t need to be the beautiful one

## TDD is not about the money/tests

More than any checking, we need to think about our software design first.

One of the things that amaze me about TDD is how we can grow our software design consciously and well, just building what is needed to make the test pass. When we are writing tests we are forced to think about the design first and how we can break it into small pieces.

## Remember: Write test to fail --> write feature to pass --> refactor for efficiency and clean code.

## Takeaways

- software design first

- Your code will be more reliable: after a change you can run your tests and be in peace

- Beginning may be hard — and that’s fine. You just need to practice!

Two books to dive into TDD:

[Test Driven Development: By Example](https://www.amazon.com.br/Test-Driven-Development-Kent-Beck/dp/0321146530)

[Growing Object-Oriented Software, Guided by Tests](https://www.amazon.com.br/Growing-Object-Oriented-Software-Guided-Tests/dp/0321503627)

---

## Recursion

Source:[Recursion](https://www.geeksforgeeks.org/recursion/)

**What is Recursion?**

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily. Examples of such problems are Towers of Hanoi (TOH), Inorder/Preorder/Postorder Tree Traversals, DFS of Graph, etc.

**What is base condition in recursion?**

In the recursive program, the solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems. 

**How a particular problem is solved using recursion?**

The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion.

**Why Stack Overflow error occurs in recursion?**

If the base case is not reached or not defined, then the stack overflow problem may arise.

> **What is Stack Overflow?**
> - When a program attempts to use more space than is available on the call stack the stack is said to overflow, typically resulting in a program crash.

**What is difference between tailed and non-tailed recursion?** 

A recursive function is tail recursive when recursive call is the last thing executed by the function. Please refer tail recursion article for details. 

**How memory is allocated to different function calls in recursion?** 

When any function is called from main(), the memory is allocated to it on the stack. A recursive function calls itself, the memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.

**What are the disadvantages of recursive programming over iterative programming?**

Note that both recursive and iterative programs have the same problem-solving powers, i.e., every recursive program can be written iteratively and vice versa is also true. The recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached. It also has greater time requirements because of function calls and returns overhead.

**What are the advantages of recursive programming over iterative programming?**

Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals, Tower of Hanoi, etc. For such problems, it is preferred to write recursive code. We can write such codes also iteratively with the help of a stack data structure. For example refer [Inorder Tree Traversal without Recursion, Iterative Tower of Hanoi.](https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion/)