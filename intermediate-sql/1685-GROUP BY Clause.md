The GROUP BY clause allows us to group together rows that have the same values in a column, then perform a summary function on the value of another column for all the rows in a group. 

For example, say we want to find the number of customers belonging to each country. So far, with the tools we have learned, we would need to write a separate query for getting the number of customers from each country. With the GROUP BY clause, however, this can be done using a single query:

`SELECT Country, COUNT(*) from  Customers GROUP BY Country`

The COUNT() function returns the number of rows in the result. The GROUP BY clause first divides the rows into groups based on the value in the Country column before the COUNT() function is applied to each group. We can also count the number of rows for a specific column instead of saying COUNT(*). For example, we could have said COUNT(CustomerID) to count the number of rows in the CustomerID column for each group, but the end result would have been the same. 

GROUP BY is one of the most useful features of SQL for Data Analysis, but it is slightly difficult to master as well since it may not be completely intuitive. Always remember that when using a GROUP BY clause, and the end result is expected to have multiple rows in each group, you must use some aggregate/summary function like COUNT(), SUM(), MIN(), MAX(),  AVG(), etc. This is necessary as each group in the result must have only one corresponding row.

### Some Examples

Below are some more examples of GROUP BY functionality, go through them and practice them yourself to get the hang of it a bit better:

`SELECT SUM(Quantity) from OrderDetails GROUP BY ProductID`
This shows the total quantity ordered for each product.

`SELECT COUNT(OrderID) from Orders GROUP BY ShipperID`
Shows the number of orders from each shipper.

`SELECT COUNT(ProductID) from Products GROUP BY CategoryID`
Show the number of Products in each Category.

`SELECT Country,COUNT(SupplierID) from Suppliers GROUP BY Country`
Number of Suppliers in each country.

These are some basic GROUP BY queries that should help you understand the concept a bit more clearly. However, Data Analysis in the real world often combines multiple clauses in a single query to get some useful insight into the data, so having the basics clear is very important. 

### Exercise Resource
Here's a good resource to help you practice GROUP BY clause usage:

https://www.w3resource.com/sql-exercises/sql-aggregate-functions.php

Questions eight and beyond are based on the GROUP BY clause.