# SQL-What is SQL?
SQL is a standard language for accessing and manipulating databases.

What Can SQL do?
SQL can execute queries against a database
SQL can retrieve data from a database
SQL can insert records in a database
SQL can update records in a database
SQL can delete records from a database
SQL can create new databases
SQL can create new tables in a database
SQL can create stored procedures in a database
SQL can create views in a database
SQL can set permissions on tables, procedures, and views

RDBMS
RDBMS stands for Relational Database Management System.

Database Tables
A database most often contains one or more tables. Each table is identified by a name (e.g. "Customers" or "Orders"). Tables contain records (rows) with data.

The SQL SELECT Statement
The SELECT statement is used to select data from a database.
The data returned is stored in a result table, called the result-set.
SELECT Syntax	
SELECT column1, column2,...
FROM table_name;

The SQL SELECT DISTINCT Statement
The SELECT DISTINCT statement is used to return only distinct (different) values.
Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

SELECT DISTINCT Syntax 
SELECT DISTINCT column1, column2, ..
FROM table_name;
SELECT DISTINCT Examples
The following SQL statement selects only the DISTINCT values from the "Country" column in the "Customers" table:
Example    SELECT DISTINCT Country FROM Customers;

The SQL WHERE Clause
The WHERE clause is used to filter records.
It is used to extract only those records that fulfill a specified condition.
WHERE Syntax 
SELECT column1, column2, …  
FROM table_name  
WHERE condition;

Example 
SELECT * FROM Customers
WHERE Country='Mexico';

The SQL AND, OR and NOT Operators
The WHERE clause can be combined with AND, OR, and NOT operators.
The AND and OR operators are used to filter records based on more than one condition:
The AND operator displays a record if all the conditions separated by AND are TRUE.
The OR operator displays a record if any of the conditions separated by OR is TRUE.
The NOT operator displays a record if the condition(s) is NOT TRUE.

AND Syntax 
SELECT column1, column2, … 
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
OR Syntax 
SELECT column1, column2, …
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
NOT Syntax 
SELECT column1, column2, …
FROM table_name 
WHERE NOT condition;
Example 
SELECT * FROM Customers  
WHERE Country='Germany' AND City='Berlin';
Example
SELECT * FROM Customers
WHERE City='Berlin' OR City='München';
Example
SELECT * FROM Customers
WHERE Country='Germany' OR Country='Spain';
 Example 
SELECT * FROM Customers 
WHERE NOT Country='Germany';

The SQL ORDER BY Keyword
The ORDER BY keyword is used to sort the result-set in ascending or descending order.
The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.
ORDER BY Syntax 
SELECT column1, column2, … 
FROM table_name 
ORDER BY column1, column2, ... ASC|DESC;
EXAMPLE 
SELECT * FROM Customers
ORDER BY Country;
EXAMPLE 
SELECT * FROM Customers 
ORDER BY Country DESC;

The SQL INSERT INTO Statement
The INSERT INTO statement is used to insert new records in a table.
INSERT INTO Syntax
It is possible to write the INSERT INTO statement in two ways:
1. Specify both the column names and the values to be inserted: 
INSERT INTO table_name (column1, column2, column3, ...)  
VALUES (value1, value2, value3, ...);
INSERT INTO syntax would be as follows: 
INSERT INTO table_name 
VALUES (value1, value2, value3, ...);
Example
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');

What is a NULL Value?
A field with a NULL value is a field with no value.
If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

How to Test for NULL Values?
It is not possible to test for NULL values with comparison operators, such as =, <, or <>.
We will have to use the IS NULL and IS NOT NULL operators instead.

IS NULL Syntax 
SELECT column_names 
FROM table_name 
WHERE column_name IS NULL;

IS NOT NULL Syntax 
SELECT column_names 
FROM table_name 
WHERE column_name IS NOT NULL;

The IS NULL Operator
The IS NULL operator is used to test for empty values (NULL values). 
SELECT CustomerName, ContactName, Address 
FROM Customers 

WHERE Address IS NULL;
The IS NOT NULL Operator
The IS NOT NULL operator is used to test for non-empty values (NOT NULL values).
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;

The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.
UPDATE Syntax 
UPDATE table_name 
SET column1 = value1, column2 = value2, … 
WHERE condition;
Example
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.
DELETE Syntax
DELETE FROM table_name WHERE condition;
Example
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';

The SQL SELECT TOP Clause
The SELECT TOP clause is used to specify the number of records to return.
The SELECT TOP clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
SELECT TOP 3 * FROM Customers;
Example
SELECT * FROM Customers
LIMIT 3;
