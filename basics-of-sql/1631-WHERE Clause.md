The WHERE clause filters out the rows that meet a specified condition or conditions and then performs the query on the extracted rows. For SELECT statements, the WHERE clause filters out the rows based on the specified conditions and only displays the rows that satisfy the condition. 

WHERE clause can also be used in other queries, like UPDATE, which allows us to change existing values in a table. Using the WHERE clause in combination with UPDATE allows us to alter the values of only those rows which satisfy a condition. For this tutorial, we will focus on using the WHERE clause in SELECT statements, but the same logic also applies to other statements.

## WHERE Clause in SELECT Statements
Let's say we want to view the details of only those Customers that belong to the USA in the Northwind Database. If we phrase this sentence in English, we would say something like this:

"I want to select all the details from the Customers table for the rows where the Country is USA."

We can then easily write the SQL query for this:

`SELECT * from Customers WHERE Country = 'USA'`

**Note**: The rules for single vs. double quotes are a bit ambiguous in SQL and depend on which software you're using. Some allow you to use them interchangeably, while others are stricter. According to the standard, string literals should be enclosed in single quotes. This includes 'USA' and any other strings with pre-defined values (that is, they are not variables). On the other hand, variable names or aliases must be enclosed in double quotes IF they have a space in the name. SQLite does not enforce this rule, so we can use single and double quotes interchangeably. 

Another example: say we want to view the Orders which were executed on 1996-08-01. We can again use the WHERE clause to do this:

`SELECT * from Orders WHERE OrderDate = '1996-08-01'`

Notice the quotes around the date in the above query. We have to do this because, in this database, the dates are stored as strings. 

## Operators in WHERE Clause
We have a few operators that can be used in the WHERE clause to define different types of conditions. Here's a list of some basic operators:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_7092a8efc9d740f48a6e0045accf079d.png)

**Note**: SQLite supports both <> and != for the 'Not equal to' operation. 

Let us look at each of these operators briefly. In all the explanations below,