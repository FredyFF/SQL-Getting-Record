## Getting Record 
This material uses the example of the Northwind database, To get records in SQL, you can use a SELECT statement along with a WHERE clause. The WHERE clause allows you to specify conditions that must be met for a record to be retrieved.

### Table of Contents
- Getting record



#### Getting Record
Use Used to connect one query file connection with one database.
USE Northwind;

The SELECT statement shows information about the column to be displayed, the FROM statement shows the data table used for this query.

In this example, this means displaying 2 columns FirstName and LastName from the Employee table

SELECT FirstName, LastName
FROM dbo.Employees;

Displays all columns of a table
SELECT *
FROM dbo.Employees;

Display columns with aliases, or replace column labels using AS
SELECT Title AS jobtitle, FirstName AS [name]
FROM dbo.Employees;
--NOTE: a key word that is already in use, such as Name, can be replaced by using the square bracket [Name], as well as for the use of more than one word with spaces.
References

Aliases can be written without using AS, that is, by using spaces only, but it is better with AS to eliminate ambiguity
SELECT Title [Job Title], FirstName [First Name]
FROM dbo.Employees;
--NOTE: Square brackets are used for column names that have more than one word and use spaces.

It can also be written using a quotation string, but this is different from an alias.
SELECT Title 'Job Title', FirstName 'First Name'
FROM dbo.Employees;

Combine more than one column into one column using CONCAT
SELECT CONCAT(TitleOFCourtesy, ' ', FirstName, ' ', LastName) AS [Complete Name], Title AS [Job Title]
FROM dbo.Employees;

Choose from more than 1 table
SELECT FirstName, CompanyName
FROM dbo.Employees, dbo.Customers;

Write table name information in front of each column to avoid ambiguity.
SELECT CONCAT(dbo.Employees.TitleOFCourtesy, ' ', dbo.Employees.FirstName, ' ', dbo.Employees.LastName) AS [Complete Name], dbo.Employees.Title AS [Job Title]
FROM dbo.Employees;

An example of ambiguity that can occur, both customers and shippers have CompanyName
SELECT dbo.Customers.CompanyName, dbo.Shippers.CompanyName
FROM dbo.Customers, dbo.Shippers;

Writing table in front of the column name can be too long, we can also create an alias in front of the table name.
SELECT CONCAT(emp.TitleOFCourtesy, ' ', emp.FirstName, ' ', emp.LastName) AS [Complete Name], emp.Title AS [Job Title]
FROM dbo.Employees AS emp;




