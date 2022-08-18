## DB Browser for SQLite
In this course, we will use a simple, lightweight software to run SQL queries - DB Browser for SQLite. There are MANY other software that can also be used instead, but some of them might seem intimidating to a beginner. DB Browser has a clean and simple interface, so we will use it in this course. The same SQL queries can also be used in pretty much any other software that supports SQL, with little to no changes. 

If this is your first time using SQL, I would recommend using the same software to get the concepts right first, and then you can later explore the differences between other software and DB Browser. 

Note: DB Browser supports a slightly cut-down version of SQL, known as SQLite. Therefore, some advanced queries are not supported by it. This will not be a problem for the content of this course, but for more advanced SQL topics, you may need to consider a different software, like MySQL or Microsoft SQL Server.

## Installing DB Browser for SQLite
DB Browser can be downloaded for various operating systems from their official website: https://sqlitebrowser.org/dl/

Once downloaded, just follow the instructions to finish installing it on your system. For the Windows installer, you can select where you want to place shortcuts. Leave the other options as-is. We will use the DB Browser(SQLite) application, not the DB Browser(SQLCipher) application. 

## DB Browser Interface
Once installed, you can open DB Browser using the shortcuts created. If you did not create any shortcuts, you can go to the directory where you installed the software (on Windows, this is the Program Files or Program Files(x86) Folder in your C: drive by default) and launch it from the DB Browser folder in that directory. 

This is what you will see the first time you launch DB Browser for SQLite:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_a3c8bd7778a844029346ececd43d3f00.png)

Before we can get started with writing SQL queries, we need to create or open a database so that we can run the queries on the data in that database. For this purpose, we have uploaded a sample database of a popular 'beginner' database for SQL - the Northwind Database. You can download the file from [here](https://github.com/dphi-tech/Datasets/blob/master/Northwind.db).

There are two ways you can open the e downloaded file in DB Browser. 

Firstly, you can open DB Browser from a shortcut or from Program Files, then go to 'Open Database' and browse to the downloaded file.

Secondly, you can directly go to the downloaded file and choose to open it using DB Browser (for this, DB Browser must be the default app for opening .db files, or you must manually choose to use DB Browser to open the downloaded file).

Once you open the .db file in DB Browser successfully, you should see something like this:

![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_f9f10c40061e4f0c9b52799f5c1d5121.png)

This tab gives you an overall structure of the database, which includes the tables in the database, the queries that were used to create the structure of that table, and if you click the arrow on the left of a table name, it will further show you the columns in that table and its characteristics/properties. Don't worry if you don't understand these yet, we'll look at them one by one.

For now, congratulations on installing DB Browser and loading up your first database! In the next topic, we'll look further into the information being displayed by DB Browser on the database.