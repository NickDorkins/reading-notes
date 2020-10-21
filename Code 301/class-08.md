# Introduction to SQL
**Source: [SQLBolt](https://sqlbolt.com/)**

## What is SQL?

**SQL, or Structured Query Language, is a language designed to allow users to query, manipulate, and transform data from a relational database.**

> This database also provides a safe and scalable storage for millions of websites and mobile applications.

Some SQL Databases: (All support SQL standard)
- QLite
- MySQL
- Postgres
- Oracle
- Microsoft SQL Server

**Relational database** - represents a collection of related (two-dimensional) tables.

> To retrieve data from a SQL database, you have to write a `SELECT` statement, also know as a *`queries`*

```
SELECT column, another_column, …
FROM mytable;
```

> This query will be a two-dimensional set of rows and columns, only with the columns that we requested.

To select all of the column names you can use an asterisk `(*)` instead of all the value names:

```
SELECT * 
FROM mytable;
```

---

## SQL Lesson 2: Queries with constraints (Pt. 1)

> In order to filter certain results from being returned, we need to use a `WHERE` clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.

| Operator	| Condition	| SQL Example | 
| --- | --- | --- |
| =, !=, < <=, >, >=	| Standard numerical operators	| col_name != 4 | 
| BETWEEN … AND …	| Number is within range of two values (inclusive)	| col_name BETWEEN 1.5 AND 10.5 | 
| NOT BETWEEN … AND …	| Number is not within range of two values (inclusive)	| col_name NOT BETWEEN 1 AND 10 | 
| IN (…)	| Number exists in a list	| col_name IN (2, 4, 6) | 
| NOT IN (…)	| Number does not exist in a list	| col_name NOT IN (1, 3, 5) | 

---

## SQL Lesson 3: Queries with constraints (Pt. 2)

> When writing `WHERE` clauses with columns containing text data, **SQL** supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching.

| Operator |	Condition |	Example |
| --- | --- | --- |
| =	| Case sensitive exact string comparison (***notice the single equals***) |	col_name = "abc" |
| != or <>	| Case sensitive exact string inequality comparison |	col_name != "abcd" |
| LIKE	| Case insensitive exact string comparison |	col_name LIKE "ABC" |
| NOT LIKE	| Case insensitive exact string inequality comparison |	col_name NOT LIKE "ABCD" |
| %	| Used anywhere in a string to match a sequence of zero or more | characters (only with LIKE or NOT LIKE) col_name LIKE "%AT%"
| --- | --------------------- | (matches "AT", "ATTIC", "CAT" or even "BATS") |
| _ |	Used anywhere in a string to match a single character (only with LIKE or NOT LIKE) |	col_name LIKE "AN_" |
| --- | --------------------- | (matches "AND", but not "AN") |
| IN (…)	| String exists in a list |	col_name IN ("A", "B", "C") |
| NOT IN (…)	| String does not exist in a list |	col_name NOT IN ("D", "E", "F") |

### Full text search dedicated libraries:
- [Apache Lucene](http://lucene.apache.org/)
- [Sphinx](http://sphinxsearch.com/)

## How does this work??? (Question 1)
```
SELECT title, director FROM movies 
WHERE title LIKE "Toy Story%";
```
> In the operator guideline table it shows that it should be written as `"%condition%"` yet when I clicked the solution it rendered as `"condition%"`

---

## SQL Lesson 4: Filtering and sorting Query results

`DISTINCT` keyword provides a convenient way to discard rows that have a duplicate column value

```
SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);
```

When an `ORDER BY` clause is specified, each row is sorted alpha-numerically based on the specified column's value. 

```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```

```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

> `LIMIT` will reduce the number of rows to return
> 
> `OFFSET` will specify where to begin counting the number rows from

---

## SQL Lesson 13: Inserting rows

### What is Schema?

In SQL, the ***database schema*** is what describes the structure of each table, and the datatypes that each column of the table can contain.

`INSERT` statement declares which table to write into, the columns of data that we are filling, and one or more rows of data to insert.

> Each row of data inserted should contain values for every corresponding column in the table. 
> 
> You can insert multiple rows at a time by just listing them sequentially.

```
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
       (value_or_expr_2, another_value_or_expr_2, …),
       …;
```

> In some cases, if you have incomplete data and the table contains columns that support default values, you can insert rows with only the columns of data you have by specifying them explicitly.

```
INSERT INTO mytable
(column, another_column, …)
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),
      …;
```

> Notice the `another_column` expression on line 2.
> 
> In these cases, the number of values need to match the number of columns specified. Despite this being a more verbose statement to write, inserting values this way has the benefit of being forward compatible.

> You can use mathematical and string expressions with the values that you are inserting.
This can be useful to ensure that all data inserted is formatted a certain way.

```
INSERT INTO boxoffice
(movie_id, rating, sales_in_millions)
VALUES (1, 9.9, 283742034 / 1000000);
```
> Notice the mathematical statement at the end of line 3 (`283742034 / 1000000`)

Insert into Table:
```
INSERT INTO movies VALUES (4, "Toy Story 4", "El Directore", 2015, 90);

INSERT INTO boxoffice VALUES (4, 8.7, 340000000, 270000000);
```
---

## SQL Lesson 14: Updating rows

`UPDATE` statement is used to update existing data.

```
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;
```

> The statement works by taking multiple column/value pairs, and applying those changes to each and every row that satisfies the constraint in the WHERE clause.

> # Pro Tip: 
> **Always write the constraint first and test it in a `SELECT` query to make sure you are updating the right rows, and only then writing the column/value pairs to update.**

```
UPDATE movies
SET year = 1999
WHERE id = 3;
```
```
UPDATE movies
SET title = "Toy Story 3", director = "Lee Unkrich"
WHERE id = 11;
```

## SQL Lesson 15: Deleting rows

`DELETE` statement deletes data from a table in the database, describes the table to act on, and the rows of the table to delete through the `WHERE` clause.

```
DELETE FROM mytable
WHERE condition;
```
> # Pro Tip:
> Like the `UPDATE` statement lesson, it's recommended that you run the constraint in a `SELECT` query first to ensure that you are removing the right rows. 
>
> **Without a proper backup or test database, it is easy to irrevocably remove data, so always read your `DELETE` statements toroughly before executing.**

## SQL Lesson 16: Creating tables

`CREATE TABLE` statement allows you to create a new database table if you have new entities and relationships to store in your database.

```
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```

> The structure of the new table is defined by its ***table schema***, which defines a series of columns. Each column has a name, the type of data allowed in that column, an optional table constraint on values being inserted, and an optional default value.

> If there already exists a table with the same name, the SQL implementation will usually throw an error, so to suppress the error and skip creating a table if one exists, you can use the `IF NOT EXISTS` clause.

| Data type |	Description |
| --- | --- |
| INTEGER, BOOLEAN	| The integer datatypes can store whole integer values like the count of a number or an age. In some implementations, the boolean value is just represented as an integer value of just 0 or 1. |
| FLOAT, DOUBLE, REAL	| The floating point datatypes can store more precise numerical data like measurements or fractional values. Different types can be used depending on the floating point precision required for that value. |
| CHARACTER(num_chars), VARCHAR(num_chars), TEXT	| The text based datatypes can store strings and text in all sorts of locales. The distinction between the various types generally amount to underlaying efficiency of the database when working with these columns. |
| --- | Both the CHARACTER and VARCHAR (variable character) types are specified with the max number of characters that they can store (longer values may be truncated), so can be more efficient to store and query with big tables. |
| DATE, DATETIME	| SQL can also store date and time stamps to keep track of time series and event data. They can be tricky to work with especially when manipulating data across timezones. |
| BLOB	| Finally, SQL can store binary data in blobs right in the database. These values are often opaque to the database, so you usually have to store them with the right metadata to requery them. |

> DOCS:
> - [MySQL](http://dev.mysql.com/doc/refman/5.6/en/data-types.html)
> - [Postgres](http://www.postgresql.org/docs/9.4/static/datatype.html)
> - [SQLite](https://www.sqlite.org/datatype3.html)
> - [Microsoft SQL Server](https://msdn.microsoft.com/en-us/library/ms187752.aspx)


| Constraint	| Description| 
| --- | --- |
| PRIMARY KEY	| This means that the values in this column are unique, and each value can be used to identify a single row in this table.| 
| AUTOINCREMENT	| For integer values, this means that the value is automatically filled in and incremented with each row insertion. Not supported in all databases.| 
| UNIQUE	| This means that the values in this column have to be unique, so you can't insert another row with the same value in this column as another row in the table. Differs from the `PRIMARY KEY` in that it doesn't have to be a key for a row in the table.| 
| NOT NULL	| This means that the inserted value can not be `NULL`.
| CHECK (expression)	| This allows you to run a more complex expression to test whether the values inserted are valid. For example, you can check that values are positive, or greater than a specific size, or start with a certain prefix, etc.
| FOREIGN KEY	| This is a consistency check which ensures that each value in this column corresponds to another value in a column in another table.
| --- |For example, if there are two tables, one listing all Employees by ID, and another listing their payroll information, the `FOREIGN KEY` can ensure that every row in the payroll table corresponds to a valid employee in the master Employee list.| 








