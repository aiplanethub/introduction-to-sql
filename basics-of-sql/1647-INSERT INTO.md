Sometimes, you may want to add more rows to an existing table in SQL. This is what the INERT INTO statement allows you to do. It is a fairly simple statement where you provide rows of data in a query, and SQL adds that data to the end of an existing table.

There are two ways in which we can use the INSERT INTO statement. One is a slightly longer way where you provide the column names and the new data, and the second is one where you just provide the new data in the exact order in which the columns already exist in the table. 

Let us look at the first way. Here, we must provide the list of column names in the same order in which we will provide the new data. Let's say we wish to add a new record to the Shippers table in the Northwind database. We can use a query like this:

`INSERT INTO Shippers(ShipperID, ShipperName, Phone) VALUES (4, "Postal Couriers", "(503) 555-8989")`
We can also use a different ordering of columns, but then we must also put our new data in the same order. 

If we wish to keep the value in a specific column NULL (provided the column allows for NULL values), we can simply skip the name of that column from the column list as well as from the new row values:

`INSERT INTO Shippers(ShipperID, ShipperName) VALUES (5, "Express Parcel")`

Next, let's look at the shorter way of adding new rows to existing tables. In this method, we do not provide column names, and the new row of data must follow the exact same order as the order of columns in the existing table.

For example, let's say we want to add a new category to the Categories table. We can do so like this:

`INSERT INTO Categories VALUES (9, "Toys", "Plastic and stuffed toys, board games")`
We can explicitly mention that the value in a column is NULL in this method as well:

`INSERT INTO Categories VALUES (10, "NA", NULL)`

**Note**: We want to keep the Northwind database in its original state on our local disks. Rather than going back and manually deleting each added row to do this, we can simply use the 'Revert Changes' button that DB Browser provides to roll back all the changes done to the tables and return the database to its last saved state. We recommend you do that now so that you do not face issues with future queries due to differences in the database.

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_a327925e8f3c4170b34c1dc17df38a6a.png)