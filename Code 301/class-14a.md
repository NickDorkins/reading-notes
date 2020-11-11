# Readings: DATABASE NORMALIZATION
Source:[Readings: DATABASE NORMALIZATION](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/)


## Coding SQL Like a Boss

When writing SQL Queries - Don't try to jump in head first and write everything from top to bottom

Break your desired results and break down the expectations into smaller sections. Get one small piece written and then write the next small piece. 

Once all of the small pieces are complete you can start to evaluate them as a larger image.

Steps to follow when writing SQL:
- Understand what results your customer expects.
- Write out request
- Plan the steps
- Verify the steps as you go

## Understand the Results

- Know the objective or desired end result 
- Ask questions 
- Clear up ambiguities or unclear instructions
- Is the data provided the scope that they desire or are there missing pieces that they did not realize?
- Probably not a good idea to make assumptions on the tasks, so once again ask a lot of questions.


### Steps any dev can take to ensure that they are meeting customer expectations.
- Agree on definitions to clear up ambiguities
- Identify calculations.
- Understand any criteria used to filter or limit the data.

> It is easier to get your query on track before you write it, rather than being a good portion through it and needing to rework it because you didn't ask the right/enough questions.

## Write out the Request

Once you know what the customer needs, you can then write the request. (**Needs must be known and established before writing the request.**)

- Write out the request in your own words. Do not use jargon, but instead, stick to an easy to understand language. If you cannot write a simple description, then that is a warning.

- No query should be complicated that you cannot describe its meaning.

- Customer requests NEED to be done in plain english because your client does not always understand industry terms/language.

Example:

> "Create a summary of all sales by year and product model for products manufactured by Adventure Works. Only include product models whose combined sales are greater than $500,000. The sales date is the sales order's OrderDate. Use the manufacturing and finshed goods flag to determine which products to include in the calculation."

Once you provide the request to the customer, ask them to go over it and ensure that they understand the contents and the expectations of the project.

> Ensure that all parties involved are in 100% agreement.

## Plan the Steps

> You “tell” a computer program what to do step-by-step, while in SQL you describe the result.

- Be intentional with your planning, start by breaking down the full picture into smaller tasks

> It may be a good idea to take those smaller tasks and break them down even smaller to get a better look at what your expected results are.

- Create a work path that guides you from one step to the next.

- Don't allow yourself to go down rabbit holes. 
> Pre planning the tasks may help keep you on track or bring you back to the path if you get diverted.

### Steps to take when planning:

**Step 1**: What core columns drive the query?

**Step 2**: Which tables house those columns? What table joins and stitch the results together?

**Step 3**: What intermediate steps are needed to complete the query? Are subqueries or other calculation required?

**Step 4**: Does the result require summarization or finishing work?

**Step 5**: Do I need to limit the summarization or results to specific summary values or ranges?

**Step 6**: Are the expectations met?

> Look at process for writing the query from the bottom up.

^^^^^These steps are repeatable for each process, but the strategy/approach may not be. Be flexible in your planning to achieve better results^^^^^

## Verify as you Go

**The idea is to slowly build up the query, per the game plan, verifying results along the way.**

**Double-check the results just to make sure your JOINS are working as expected and you are returning “good” data.**

> Look up explaination for JOINS!

### **Once you are comfortable with the core data, start adding the *WHERE* clause.**

**Next: slowly add in the elements needed in the final query.**

### REMEMBER: you can always verify the small pieces as you add them in. It's easier than getting almost done and realizing you broke something and have no idea where to look.

Next add in the GROUP BY statement so that the query knows what values to use when rendering the final results.

## Conclusion
Keep in mind that every query is different, So the steps taken, are not always the same- but the approach is!

When facing difficult or complex SQL queries, do not try to write everything all at once. Instead, try to get a foundation in place and then build and verify small changes as you go.

Getting these small wins give you confidence, and help you know you are on the right track.

Summary:
- Make sure you understand the query. Write it out in simple language to make sure you understand.
- Confirm the request with the customer.
- Once you are good to go, get a core query in place and verify you are pulling in the correct data.
- From there, add to your query slowly by verifying results along the way.

I think you may find this approach better and takes away some stress and make it more enjoyable to
write queries.










<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
.