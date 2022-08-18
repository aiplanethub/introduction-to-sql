## Database Structure

As you may recall from the previous topic, once we load a database into DB Browser, the first page we will see looks something like this:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_d0483f63858a44efb60e761281d27490.png)

Here, each entry in the 'Tables' category is a table in the database, and each entry within a table is a column of that table. So, for example, the Northwind Database has a table called 'Customers', and this table has 7 columns, 'CustomerID', 'CustomerName','ContactName', etc. 

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_b82c86bddadd4166b2ea849d6b3e3fd1.png)

The 'Type' column in the information shown tells us the data type of each column. This is something we must define while creating the table structure. If you look at the 'Schema' column, you will find the SQL query that was used to define the table structure for each table. Take a closer look at one of these queries, and you'll find that each Column name is immediately followed by its data type. 

## Column Constraints

You might also notice other phrases in that query, like 'PRIMARY KEY' or 'AUTOINCREMENT'. These phrases are called Column Constraints or simply Constraints. Let's look at what constraints we can use when defining columns, and what they mean:

### NOT NULL
This constraint ensures that the column does not contain any NULL values. NULL values basically represent values that are missing or unknown. For some columns, we cannot allow any value to be missing, which is where this constraint comes into play. For example, if we have a table where each row represents a bank transaction, we will not want to allow the 'Amount' column to have NULL values.

### UNIQUE
The UNIQUE constraint ensures that a column does not have duplicate values, that is, each row has a unique value in that column. Again, this can be required in certain cases where duplication does not make logical sense and can cause problems. For example, we cannot have duplicates in the 'Roll Number' column of a table that represents the students of a single class.

### PRIMARY KEY
The PRIMARY KEY constraint combines both the NOT NULL and the UNIQUE constraints into one. Columns which have this constraint enforce every row to have a unique value and no null values are allowed. Primary Keys serve to uniquely identify every row in a table. We will learn more about their importance later. 

### FOREIGN KEY
We have learnt that tables an often be related or linked in a relational database. The primary key and foreign key constraints are what help us identify and define these links between tables. Again, we will look at this in more detail later.

### CHECK
The CHECK constraint is used to make sure that every value in a column satisfies a pre-defined condition. This can be helpful in avoiding errors during data entry. For example, if a column represents percentage marks of a student in a subject, we can use the CHECK constraint to make sure the value provided is between 0 and 100.

### DEFAULT
This constraint allows us to provide a default value for a column, in case there is a missing value. It is useful if we know that all the missing values are only due to a specific scenario, and we want to assign a value to that scenario. For example, a missing value in 'Test Score' column in a student database may signify that the student was absent for that test, and we can automatically allot a Test Score of zero for this case using the DEFAULT constraint.

### AUTOINCREMENT
This is used for columns where the next row's value is the previous row's value plus one. This is often useful for ID-type columns, where we want each row to have a unique value attached to it. For this reason, AUTOINCREMENT columns are also suitable PRIMARY KEY candidates. 

## Data Types

Each version of SQL has slightly different implementation of Data Types. There is also a difference between SQL and SQLite in terms of data types. To avoid confusing you with all the different implementations, we will currently only focus on the data types present in SQLite. To learn about Data Types in some other popular SQL software, you can visit this link: https://www.w3schools.com/sql/sql_datatypes.asp

### NULL
The Null data type is fairly straightforward - it represents missing or unknown data. 

### INTEGER
Integer data type can have signed integer values. How much memory an Integer value takes is dynamically allotted by SQLite based on the magnitude of the value itself. It can vary between 0, 1, 2, 3, 4, 6 or 8 bytes. 

### REAL
The Real data type is used to store floating point or decimal numbers. It takes up 8 bytes of memory.

### TEXT
This is text data, similar to Strings in Python. It can store a sequence of characters in the same encoding format that the entire database uses, be it UTF-8, UTF-16BE, or UTF-16LE.

### BLOB
This is a data type that stores the input as it is in memory, without applying any encoding. It can be useful for storing entire files in the database as it is, like images, audio, video, etc.

### Boolean Data
Newer versions of SQLite (3.23.0 and later) recognize the "TRUE" and "FALSE" keywords, but it ultimately stores these as 1 and 0 in memory respectively. SQLite does not have a separate Boolean Data Type. 

### Date and Time
SQLite also does not have separate data types for Date and Time Data. Instead, it uses built-in Date and Time functions to convert the other data types into Date and Time values. It can store Date and Time values as TEXT in ISO8601 format ("YYYY-MM-DD HH:MM:SS.SSS"), or as REAL by counting the number of days passed since noon in Greenwich on November 24, 4714 B.C., or as INTEGER in Unix format, that is, counting the number of seconds that have passed since midnight of 1st January 1970 UTC. All of these formats can then be converted into human-readable formats by using various Date and Time Functions available in SQLite. 

For more detailed information about SQLite Data Types, you can look at the official documentation: https://www.sqlite.org/datatype3.html

## Browse Data

The 'Browse Data' tab allows you to open up a specific table and glance over the actual data present in that table. This can be useful for when you want to design a query and need to look at what the data in each column is. You can also perform some basic actions through the UI itself, like filtering, sorting, adding or deleting records, etc. We will nonetheless soon be learning SQL queries for performing these actions. 



![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_c7060825c1d24bfba3c567cfd7583bde.png)


## Execute SQL

Finally, this tab is where most of the action will be happening throughout this course. This tab allows you to create a .sql file, in which you can write SQL queries and also execute them on the currently open database. 







![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_62294bde00324c4fa0bf9154a48864e7.png)





This tab includes options related to the .sql file, like opening multiple SQL files, creating a new file, saving or printing the current file. It also includes buttons for executing the selected SQL statements, executing all the statements, and for interrupting the execution of a statement. 

Further below, you will find two more windows - the second window is where you will find the output of your SQL query, if there is any. Finally, the last window will show you the result of running the query - this is where you will find error messages if something goes wrong with your code, and if the query runs successfully, it will show a sort of summary of the result. Here's an example:





![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_192d7d24401b4944b114a26972de213c.png)




Don't worry if you don't understand the query yet, we will cover that soon. Just have a look at what each window's purpose is. Feel free to explore the interface and familiarize yourself with it, and even explore a few queries if you wish to do so - the database that you have downloaded will not be affected by any queries until and unless you click on the 'Write Changes' button on the top. Even if something goes wrong with a query, you can always re-download the database and start fresh, so go ahead and experiment :)