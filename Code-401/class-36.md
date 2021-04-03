# Class 36: DSA Review

## [Reading: Whiteboard Advice](https://hackernoon.com/the-best-whiteboard-interview-advice-i-ever-received-3ebbfa72e4a)

**Whether you agreee or disagree with whiteboard interviews, as a developer in the tech industry it is a process that you are going to go through if you want to be employed by a company.**

## <u>The Advice: Communicate!</u>

Communicating what you are doing during a whiteboard shows the interviewer that you are capable of thinking about a problem and solving it without any assistance, even if you do not actually complete the whiteboard during this process, you will at least illustrate your thought process to the perspective employer.

## <u>What Do You Mean Communicate?</u>

You should not be getting your problem domain and going straight into coding a solution (unless that is specifically requested), however you should be using the following checklist to ensure that you can look at the problem not only at a birds eye view but at ground level as well.

Whiteboard Checklist:

- Problem Domain <span style="color:red">(?)</span>
- Identify `Input`
- Identify `Output`
- Edge Cases <span style="color:red">(?)</span>
- Visual
- Algorithm <span style="color:red">(?)</span> - Scope: Birds Eye View
- Pseudocode - Scope: Standing on top of a building
- Big-O
- Code - Scope: Ground Level
- Verification <span style="color:red">(?)</span>

> Note: The red question mark <span style="color:red">(?)</span> indicates the times at which you should be asking any clarifying questions that you may have.

> You should be verbally talking the interviewer through the steps that you are taking and ensure that you are taking them along with the adventure instead of sitting there in silence writing the solution out. This can be interpreted in many different ways and you never want a negative interpretation.

## <u>First, Restate the Question</u>

To prove that you understand what the interviewer is asking of you, restate the question. With restating the question, you are seeking affirmation that your understanding of the problem domain meets the interviewers expectations.

During this, you may find that you don't quite have the correct interpretation of the question and may need some clarification.

Example restatement if your problem domain is fizz-buzz:

```
“So I’d like to restate the problem to you to ensure I understand what you’re looking for. The sole parameter for my function will be an integer. The sole output of my function will be an incrementing array, starting from the number 1 and ending at the input number.

If a number is a multiple of 3, the output will instead be `fizz`. If a number is a multiple of 5, the output will instead be `buzz`. However, if the output is a multiple of both 3 and 5, the output will instead be `fizzbuzz`. Is my understanding correct?”
```

Restating the problem domain will never hurt you, but it may keep you from heading down the wrong path and being too far away from the expected results to salvage the whiteboard by the time that you figure it out.

## <u>Ask About Edge Cases</u>

**Still not ready to write the code for this whiteboard.**

Once you understand the `input` and expected `output` you can then think about which method you are going to want to use to solve this problem and possible senarios you may run into that, if not addressed, may cause issues once you have everything coded out. 

Example of an edge case would be if you are expected to write a function that takes in a string, "do the thing", and return a string. 

What happens if the interviewer asks you to pass an integer as an input? 
- ***Has this been handled?*** 
- ***Does it need to be handled?*** 
- ***Can you assume that all inputs will be a string?***

Clarifying questions can save you time and allow you to plan error handling and handling different types of data. This shows an analytical thought process and that you work hard to prevent bugs.

## <u>Ask About Test Cases</u>

**No code yet.**

Asking about test cases is like restating the problem domain, this can never hurt you, however this can have some different effects on your interviewer:

- The interviewer may be expecting you to ask about test cases, as it is important to them that you know about tests and are able to acknowledge them in advance so that your solution is prepared to handle it.

- You may have an interviewer that is not expecting you to handle tests and like that you are acknowledging them in the beginning to prevent refactoring later.

## <u>Write Algorithm and Ask If It Makes Sense</u>

**Closer but still not writing code.**

When writing your algorithm you want to write everything in plain English, you want to use an extremely minimal amount of literal code in this section. You're not writing paragraphs or full sentences even, you want to write what I call "statements of intent".

Algorithm Example:

> "define a function called `algorithm()` passing in the value `self` and `input`"

Notice that the only literal code was the function name? I prefer this method because as you go through the next processes, you can retain those values and use them as you continue.

## <u>Write Pseudocode and Ask If It Makes Sense</u>

Pseudocode is a hybrid between the algorithm and actual code. For this you should be using pointers to indicate which values are being passed at a given time.

Pseudocode Example:

> def algorithm() <-- self & value


> This step should look closer to code, however it is important to note that you are not to be writing code yet. 





## [Reading: 6 Tips](https://blog.usejournal.com/6-tips-to-ace-a-whiteboard-programming-interview-f06c1b378bc6)

## [Video: Engineering Interview Process Deconstructed](https://www.youtube.com/watch?v=KdXAUst8bdo)