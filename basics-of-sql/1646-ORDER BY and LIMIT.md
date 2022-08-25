## ORDER BY

The ORDER BY keyword allows us to tell SQL which column it should use to sort the results. We can also give multiple columns in the ORDER BY clause. In such a case, the first column we provide is used to sort the results first, then if there are any ties, the next column is used to break those ties, and so on. 

Take an example: We wish to see details of Orders, and sort the results such that orders with larger quantities are shown first, and those with lesser quantities are shown later (in other words, descending order of quantity). We can do so using this query:

`SELECT * from OrderDetails ORDER BY Quantity DESC`
The DESC keyword tells SQL to sort in descending order. The default order is ascending, so we usually don't explicitly mention it if we want to sort in ascending order, but if we do want to explicitly mention it, we can use the keyword ASC:

`SELECT * from OrderDetails ORDER BY Quantity ASC`
This will return the same rows but arranged in ascending order by Quantity.

Of course, we can also combine multiple clauses in SQL if we require it/ Say, for example, we want to see the details of all orders with a Quantity less than 50, arranged in descending order by Quantity. We can combine the WHERE and ORDER BY clauses to achieve this:

`SELECT * from OrderDetails WHERE Quantity < 50 ORDER BY Quantity DESC`
A certain order must be followed when combining clauses in a single query. In the above query, for example, if we wrote the ORDER BY clause first and the WHERE clause later, SQL would have thrown an error. You can try it out:

`SELECT * from OrderDetails ORDER BY Quantity DESC WHERE Quantity < 50 -- This query will throw an error`
The correct order of clauses for a SELECT statement is:
SELECT -> FROM -> WHERE -> GROUP BY -> HAVING -> ORDER BY -> LIMIT. There are some more advanced clauses as well, but these are the basic ones that you should know for now. In this course, we will discuss all of these clauses.

Now that we have discussed ORDER BY, let's move to the next simple clause - LIMIT.

## LIMIT

The LIMIT clause is simply used to restrict the number of rows that can be displayed in the output. If you have learned about the Pandas library in Python, LIMIT is essentially like the argument you provide to the .head() method in Pandas - telling the method how many rows from the top it should display.

Consider the last working query we provided on this page, reiterated below:

`SELECT * from OrderDetails WHERE Quantity < 50 ORDER BY Quantity DESC`
The result has 454 rows. We might only want to have a glance at the table structure, for which we don't need SQL to display the entire 454-row table. Instead, we can ask SQL to just show the first, say, 10 rows. This can be done using the LIMIT keyword:

`SELECT * from OrderDetails WHERE Quantity < 50 ORDER BY Quantity DESC LIMIT 10`
The LIMIT keyword is useful if you have a very big table and don't want to unnecessarily burden the database and the computer with showing a very long result, and instead show just a few rows at a glance. It is not very useful for smaller tables like the ones in the Northwind Database. Nonetheless, it is better to practice these concepts on smaller tables and have them handy for when you do start working with larger databases.