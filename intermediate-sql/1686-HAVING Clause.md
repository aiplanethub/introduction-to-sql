The HAVING Clause is used to apply a condition before an aggregate function is executed on the rows. It is used in conjunction with the GROUP BY clause to filter out the rows in each group based on some condition.

Now, you might remember another keyword that seems to serve a similar purpose - the WHERE keyword. However, the WHERE and HAVING clauses serve different purposes. The WHERE function cannot be used with aggregate functions - it excludes rows based on the value stored in the table, not based on the result of an aggregate function. In simple terms, the WHERE clause excludes rows from the result _before groups are created, and aggregate values are calculated,_ while the HAVING clause filters out rows after the grouping is done and the aggregate function's results are calculated. 

For example, consider the query we defined on the previous page to get the quantity of each product that was ordered:

`SELECT SUM(Quantity) from OrderDetails GROUP BY ProductID`

Now, let's say we want to fetch the quantity only in those cases where the total quantity ordered is more than 250. Let's try using the WHERE clause:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_15d79281991045dd8fb13c02cbbda056.png)

As you can see, this throws an error because WHERE cannot be used with aggregate functions like SUM(). Now, let's try the HAVING clause:

`SELECT ProductID, SUM(Quantity) from OrderDetails GROUP BY ProductID HAVING SUM(Quantity) > 250`
This query will give you the desired result. This is the usage of the HAVING clause - filtering rows after grouping and aggregating the values.