## What is the SELECT command?

The SELECT command is one of the most used commands when it comes to data science. It is used to display a table partly, fully, or by first modifying data in a table using some logic and then displaying it. 

Whenever we want SQL to display a result, we must use the SELECT command. Even if we want to only print the outcome of a simple mathematical operation, say, 5+2, we must still use the SELECT keyword. 

**NOTE**: SQL is not a case-sensitive language. This means that Select, select, SELECT, and even SeLeCt are all treated as the same word. We usually prefer writing SQL keywords in all capitals, but it is not necessary to do so. 

## Basic SELECT queries

Let us first print the result of a simple mathematical operation using the SELECT keyword. In the Execute SQL section of DB Browser, execute the following line:

`SELECT 5+2`

You will see the output printed as a table in the window just below the code editor.

Now, let's try to print a single column from the 'Customers' table from the Northwind Database.  If we wanted to phrase this sentence in English, we would say something like this:

"I want to SELECT the PostalCode column FROM the Customers table."

SQL syntax is very similar to English, except it drops out the extra words and only keeps the bare minimum required to make sense of your requirement. The query for performing the above action is:

`SELECT PostalCode FROM Customers`

Since SQL is not case-sensitive, you can even write the column and table names in any case, and the result will be the same. Try this out yourself!

Now, to print out more than one column, we simply have to separate them by commas:

`SELECT Address, PostalCode, CustomerName FROM Customers`
Output:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_408d4d670d2b41f3a7fbc19d5c1ecdfa.png)

Notice here that the order of columns in the output is the same order that we use in the query, not the order in which the columns occur in the original table. 

Now, imagine we have a table with many columns. It would be very time-consuming to list out all the columns, separated by commas, if we want to print the entire table as-is. For this purpose, SQL has a shortcut for selecting 'everything' from a table. This shortcut is the character '*'. When reading an SQL query, you can interpret a '*' as 'everything' or 'all'. Therefore, the query:

`SELECT * from Customers`

can be interpreted by us as "Select everything from Customers table", which is exactly what the query does. 

### Concatenation

In the Customers table, we have a separate column for City, and a separate one for Country. Let's say we want to display the Name of the Customers, and then his City and Country in a single column in the "City, Country" format. We can easily do this using the concatenation in SQL, which joins two or more strings into a single value. The SQLite concatenation operator is "||" (double pipe characters). 

`SELECT CustomerName, City || ", " || Country FROM Customers`

NOTE: Some implementations of SQL do not support the double pipe for concatenation. We can instead use the CONCAT( ) function, where you can provide column names and strings as inputs. For our case, it would look something like this: CONCAT( City, ", ", Country). SQLite does not support CONCAT( ). 



![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_1e654b86a62d4f809cf1249a019455af.png)



### Aliases

In the output to the above query, we see that the column name of the second column is the exact code used to generate that column. It does not look good, especially if we might want to save the result as a separate table or CSV file and use it elsewhere. SQL allows us to give custom names to each column in our output using the 'AS' keyword:

`SELECT CustomerName, City || ", " || Country AS Location FROM Customers`








![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_64eabac4cf4d45c29e75c00454612a16.png)






Much better! These custom names that we give to columns (and we can even give them to tables) are called aliases.

Tip: the 'AS' keyword is actually optional when giving aliases, but it makes your query more readable if you use it. Try running the last query we gave you, but remove the 'AS' keyword from it, and you'll see the result is the same! Just make sure your alias isn't the same as an existing column in the table :P

## SELECT DISTINCT

Sometimes, we may want to return only the unique values from a column. For example, we want to know all the countries from which we have entries in the Customers table. A simple SELECT statement would not be a good way to do this, as it would have many duplicate entries.

The SELECT DISTINCT statement lets us return unique values from a column:

`SELECT DISTINCT Country from Customers`