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

Let us look at each of these operators briefly. In all the explanations below, returning 'True' means that the row satisfies the condition and the query is performed on it, and returning 'False' means that the row does not satisfy the condition and is therefore excluded from the query execution. 

### = operator
Checks for equality of two values. Returns True if the two values are equal and False otherwise. We have already seen this operator in action in the introductory examples.

### > operator
Returns True if the value on the left is larger than the value on the right and False otherwise. This operator is generally used for numeric columns, but it can be used for string comparison as well. 

In string comparison, each letter of the strings is compared one by one. The letter that comes later in alphabetical order has a higher value. If all the letters are the same until the end of one of the strings, the larger string is given a higher value. For example, 'USAmerica' > 'USA'. However, 'V' > 'USA' because V comes after U in the alphabet; therefore, the first letter itself is larger in the first string and the first string is considered 'larger'. 

This operator also works well with dates. If we want to see details of Orders that occurred after, say, 1997-01-01, we can use this operator like this:

`SELECT * from Orders WHERE OrderDate > '1997-01-01'`
Note that the Orders that occurred ON 1997-01-01 are NOT included in the results, as we are looking for strictly larger dates only. 

### < operator
Return True if the value on the left is smaller than the value on the right and False otherwise. It can be used in all the same ways as the < operator to check for strictly smaller values. For example, if we want to find the Order details for the orders that had a Quantity less than 5, we can find this information from the OrderDetails table using this query:

`SELECT * from OrderDetails WHERE Quantity < 5`
Again, note that Orders with Quantity = 5 are NOT included in the results. 

### >= operator
Returns True if the value on the left is greater than or equal to the value on the right. It is similar to the > operator but allows you to include the 'edge' value in the returned results. 

For example, let's say we want to see details of the products whose price is greater than or equal to 46. We can do so using this query:

`SELECT * from Products WHERE Price >=46`
Notice that the product with Price = 46 is also included in the resulting rows.

### <= operator
Return True if the value on the left is less than or equal to that on the right. Similar to the < operator but allows you to include the 'edge' value in the returned results. 

Using the example in the >= operator section, try to design a query to display the details of Products with a Price less than or equal to 7. You should get a result with 4 rows, including a product with Price = 7.

### <> or != operator
Returns True if the value on the left and the one on the right are NOT equal and False if they are equal.

This can be useful if we want to exclude only one or two values from a Column with many values. For example, say we want to see customer details of all customers except the ones in the USA. Instead of creating a long list of all the countries present in the database and excluding the USA from it, we can use the not equal operator:

`SELECT * from Customers WHERE Country != 'USA'`
or
`SELECT * from Customers WHERE Country <> 'USA'`
The <> and != operators are equivalent and can be used interchangeably.

### BETWEEN operator
Returns True if the value lies within a specified range and False otherwise. Both edge values of the range are also included. 

For example, say we want to view details of Orders that happened between 1996-12-25 and 1997-01-01. Instead of defining two conditions, one for each 'edge' value, we can use the BETWEEN operator to simplify the task:

`SELECT * from Orders WHERE OrderDate BETWEEN '1996-12-25' AND '1997-01-01'`
Note that Orders made ON 1996-12-25 and 1997-01-01 are included in the resulting rows.