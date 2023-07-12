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

SQL uses:
• Data definition: It is used to define the structure and organization of the
stored data and relationships among the stored data items.
• Data retrieval: SQL can also be used for data retrieval.
• Data manipulation: If the user wants to add new data, remove data, or modifying in
existing data then SQL provides this facility also.
• Access control: SQL can be used to restrict a user’s ability to retrieve, add, and
modify data, protecting stored data against unauthorized access.
• Data sharing: SQL is used to coordinate data sharing by concurrent users, ensuring
that changes made by one user do not inadvertently wipe out changes made at
nearly the same time by another user.
SQL also differs from other computer languages because it describes what the
user wants the computer to do rather than how the computer should do it. (In more
technical terms, SQL is a declarative or descriptive language rather than a
procedural one.) SQL contains no IF statement for testing conditions, and no GOTO,
DO, or FOR statements for program flow control. Rather, SQL statements describe
how a collection of data is to be organized, or what data is to be retrieved or added
to the database. The sequence of steps to do those tasks is left for the DBMS to
determine.


Features of SQL:
• SQL may be utilized by quite a number of users, which include people with very
little programming experience.
• SQL is a Non-procedural language.pg. 3 | HIMANSHU KUMAR(LINKEDIN)
• We can without difficulty create and replace databases in SQL. It isn't a timeconsuming process.
• SQL is primarily based totally on ANSI standards.
• SQL does now no longer have a continuation individual.
• SQL is entered into SQL buffer on one or extra lines.
• SQL makes use of a termination individual to execute instructions immediately.
It makes use of features to carry out a few formatting.
• It uses functions to perform some formatting.


Rules for SQL:
• A ';' is used to end SQL statements.
• Statements may be split across lines but keywords may not.
• Identifiers, operator names, literals are separated by one or more spaces or other
delimiters.
• A comma(,) separates parameters without a clause.
• A space separates a clause.
• Reserved words can not be used as identifiers unless enclosed with double quotes.
• Identifiers can contain up to 30 characters.
• Identifiers must start with an alphabetic character.
• Characters and date literals must be enclosed within single quotes.
• Numeric literals can be represented by simple values.
• Comments may be enclosed between /* and */ symbols and may

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

The SQL MIN() and MAX() Functions
The MIN() function returns the smallest value of the selected column.

The MAX() function returns the largest value of the selected column.

MIN() Syntax
SELECT MIN(column_name)
FROM table_name
WHERE condition;

MAX() Syntax
SELECT MAX(column_name)
FROM table_name
WHERE condition;

EXAMPLE
SELECT MIN(Price) AS SmallestPrice
FROM Products;

EXAMPLE
SELECT MAX(Price) AS LargestPrice
FROM Products;

The SQL COUNT(), AVG() and SUM() Functions
The COUNT() function returns the number of rows that matches a specified criterion.

COUNT() Syntax
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
The AVG() function returns the average value of a numeric column. 

SELECT COUNT(ProductID)
FROM Products;


AVG() Syntax
SELECT AVG(column_name)
FROM table_name
WHERE condition;
The SUM() function returns the total sum of a numeric column. 

SELECT AVG(Price)
FROM Products;


SUM() Syntax
SELECT SUM(column_name)
FROM table_name
WHERE condition;

SELECT SUM(Quantity)
FROM OrderDetails;

The SQL LIKE Operator
The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:

 The percent sign (%) represents zero, one, or multiple characters
 The underscore sign (_) represents one, single character

 LIKE Syntax
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;

LIKE Operator	Description
WHERE CustomerName LIKE 'a%'	Finds any values that start with "a"
WHERE CustomerName LIKE '%a'	Finds any values that end with "a"
WHERE CustomerName LIKE '%or%'	Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'	Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a_%'	Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%'	Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName LIKE 'a%o'	Finds any values that start with "a" and ends with "o"

SQL Wildcard Characters
A wildcard character is used to substitute one or more characters in a string.

Wildcard characters are used with the LIKE operator. The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

Wildcard Characters in MS Access
Symbol	Description	Example
*	Represents zero or more characters	bl* finds bl, black, blue, and blob
?	Represents a single character	h?t finds hot, hat, and hit
[]	Represents any single character within the brackets	h[oa]t finds hot and hat, but not hit
!	Represents any character not in the brackets	h[!oa]t finds hit, but not hot and hat
-	Represents any single character within the specified range	c[a-b]t finds cat and cbt
#	Represents any single numeric character	2#5 finds 205, 215, 225, 235, 245, 255, 265, 275, 285, and 295

The following SQL statement selects all customers with a City starting with "ber":

ExampleGet your own SQL Server
SELECT * FROM Customers
WHERE City LIKE 'ber%';
The following SQL statement selects all customers with a City containing the pattern "es": 

Example
SELECT * FROM Customers
WHERE City LIKE '%es%';
Using the _ Wildcard
The following SQL statement selects all customers with a City starting with any character, followed by "ondon":

Example
SELECT * FROM Customers
WHERE City LIKE '_ondon';
The following SQL statement selects all customers with a City starting with "L", followed by any character, followed by "n", followed by any character, followed by "on":

Example
SELECT * FROM Customers
WHERE City LIKE 'L_n_on';

The SQL IN Operator
The IN operator allows you to specify multiple values in a WHERE clause.

The IN operator is a shorthand for multiple OR conditions.

IN Syntax
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);

The following SQL statement selects all customers that are located in "Germany", "France" or "UK":

ExampleGet your own SQL Server
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
The following SQL statement selects all customers that are NOT located in "Germany", "France" or "UK":

Example
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
The following SQL statement selects all customers that are from the same countries as the suppliers:

Example
SELECT * FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);

The SQL BETWEEN Operator
The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

The BETWEEN operator is inclusive: begin and end values are included. 

BETWEEN Syntax
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

The following SQL statement selects all products with a price between 10 and 20:

ExampleGet your own SQL Server
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;
The following SQL statement selects all products with a price between 10 and 20:

Example Get your own SQL Server
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;

NOT BETWEEN Example
To display the products outside the range of the previous example, use NOT BETWEEN:

Example
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;

The following SQL statement selects all products with a price between 10 and 20. In addition; do not show products with a CategoryID of 1,2, or 3:

Example
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID NOT IN (1,2,3);


SQL Aliases
SQL aliases are used to give a table, or a column in a table, a temporary name.

Aliases are often used to make column names more readable.

An alias only exists for the duration of that query.

An alias is created with the AS keyword.

Alias Column Syntax
SELECT column_name AS alias_name
FROM table_name;
Alias Table Syntax
SELECT column_name(s)
FROM table_name AS alias_name;

The following SQL statement creates an alias named "Address" that combine four columns (Address, PostalCode, City and Country):

Example
SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;
Note: To get the SQL statement above to work in MySQL use the following:

SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
FROM Customers;

SQL JOIN
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Let's look at a selection from the "Orders" table:

OrderID	CustomerID	OrderDate
10308	    2	        1996-09-18
10309    	37       	1996-09-19
10310    	77	        1996-09-20
Then, look at a selection from the "Customers" table:

CustomerID	   CustomerName	                       ContactName	                   Country
1	         Alfreds Futterkiste    	             Maria Anders	                    Germany
2	         Ana Trujillo Emparedados y helados    Ana Trujillo                    Mexico
3	         Antonio MorenoTaquería             	Antonio Moreno                       	Mexico


Example Get your own SQL Server
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;

Different Types of SQL JOINs

(INNER) JOIN: Returns records that have matching values in both tables
LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
SQL INNER JOIN  SQL LEFT JOIN  SQL RIGHT JOIN  SQL FULL OUTER JOIN


INNER JOIN Syntax
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

Example Get your own SQL Server
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;

LEFT JOIN Syntax
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;

ExampleGet your own SQL Server
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;

RIGHT JOIN Syntax
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;

ExampleGet your own SQL Server
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;

FULL OUTER JOIN Syntax
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;

Self Join Syntax
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;

SQL Self Join Example
The following SQL statement matches customers that are from the same city:

ExampleGet your own SQL Server
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER BY A.City;


The SQL UNION Operator
The UNION operator is used to combine the result-set of two or more SELECT statements.

Every SELECT statement within UNION must have the same number of columns
The columns must also have similar data types
The columns in every SELECT statement must also be in the same order
UNION Syntax
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
UNION ALL Syntax
The UNION operator selects only distinct values by default. To allow duplicate values, use UNION ALL:

SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;

SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers
ORDER BY City;

The SQL GROUP BY Statement
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

GROUP BY Syntax
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);

SQL GROUP BY Examples
The following SQL statement lists the number of customers in each country:

ExampleGet your own SQL Server
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;

Example
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;

GROUP BY With JOIN Example
The following SQL statement lists the number of orders sent by each shipper:

Example
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders FROM Orders
LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID
GROUP BY ShipperName;

The SQL HAVING Clause
The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.

HAVING Syntax
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);

SQL HAVING Examples
The following SQL statement lists the number of customers in each country. Only include countries with more than 5 customers:

ExampleGet your own SQL Server
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;


More HAVING Examples
The following SQL statement lists the employees that have registered more than 10 orders:

Example
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM (Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 10;

The SQL EXISTS Operator
The EXISTS operator is used to test for the existence of any record in a subquery.

The EXISTS operator returns TRUE if the subquery returns one or more records.

EXISTS Syntax
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);

SQL EXISTS Examples
The following SQL statement returns TRUE and lists the suppliers with a product price less than 20:

ExampleGet your own SQL Server
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);

The SQL ANY and ALL Operators
The ANY and ALL operators allow you to perform a comparison between a single column value and a range of other values.

The SQL ANY Operator
The ANY operator:

returns a boolean value as a result
returns TRUE if ANY of the subquery values meet the condition
ANY means that the condition will be true if the operation is true for any of the values in the range.

ANY Syntax
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition);

The SQL SELECT INTO Statement
The SELECT INTO statement copies data from one table into a new table.

SELECT INTO Syntax
Copy all columns into a new table:

SELECT *
INTO newtable [inexternal]
FROM oldtable
WHERE condition;
