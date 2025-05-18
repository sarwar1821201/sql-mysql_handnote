# We will learn about SQL everything

SQL is a standard language for storing, manipulating and retrieving data in databases.
My SQL tutorial will teach you how to use SQL in: MySQL, SQL Server,  Postgres, and other database systems.

## What is SQL?
 - SQL stands for Structured Query Language
 - SQL lets you access and manipulate databases
 - SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987

 ### What can SQL do?

 - SQL can execute queries against a database
- SQL can retrieve data from a database
- SQL can insert records in a database
- SQL can update records in a database
- SQL can delete records from a database
- SQL can create new databases
- SQL can create new tables in a database
- SQL can create stored procedures in a database
- SQL can create views in a database
- SQL can set permissions on tables, procedures, and views 

## Some of The Most Important SQL Commands

- SELECT - extracts data from a database
- UPDATE - updates data in a database
- DELETE - deletes data from a database
- INSERT INTO - inserts new data into a database
- CREATE DATABASE - creates a new database
- ALTER DATABASE - modifies a database
- CREATE TABLE - creates a new table
- ALTER TABLE - modifies a table
- DROP TABLE - deletes a table
- CREATE INDEX - creates an index (search key)
- DROP INDEX - deletes an index

## Website
- W3 school--->  
<https://www.w3schools.com/sql/default.asp>
- Postgresql    
<https://www.postgresql.org/about/>

## The SQL SELECT Statement
The SELECT statement is used to select data from a database. It means select all rows from the table, If you want to return all columns, without specifying every column name, you can use the SELECT * syntax:
  #### code for select everything from table query
  `select * from employees;`

  ![select query image](/img/select_command.PNG)

  ## The SQL SELECT DISTINCT Statement
 SELECT DISTINCT column1, column2, ...
FROM table_name;

Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

`select distinct from employees;`

  ![select query image](/img/distinct.PNG)


  ## The SQL WHERE Clause

The WHERE clause is used to filter records.
It is used to extract only those records that fulfill a specified condition.

## code for where clause

 `SELECT * FROM employees WHERE salary>5000;`

  SELECT column1, column2, ...
FROM table_name
WHERE condition;

   ![select query image](/img/where_clause.PNG)

   ## The SQL ORDER BY
 The ORDER BY keyword is used to sort the result-set in ascending or descending order.The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

 ### code for order by query
 `SELECT * FROM employees ORDER BY salary DESC, country ASC;`

![select query image](/img/order_by.PNG)

## The SQL AND Operator
The WHERE clause can contain one or many AND operators.

The AND operator is used to filter records based on more than one condition, like if you want to return all employees from usa that starts with the letter 'G':


## code for and operator
`SELECT * FROM employees WHERE country="usa" AND salary>5000;`

![select query image](/img/and.PNG);

## The SQL OR Operator
The WHERE clause can contain one or more OR operators.

The OR operator is used to filter records based on more than one condition, like if you want to return all customers from Germany but also those from Spain:

SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

## code for or operator
`SELECT * FROM employees WHERE country="usa" OR city="london";`

![select query image](/img/or.PNG);

### The NOT Operator

The NOT operator is used in combination with other operators to give the opposite result, also called the negative result.

SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

### code for NOT Operator

`SELECT * FROM employees WHERE NOT country="usa";`
`SELECT * FROM employees WHERE name NOT LIKE 'l%';`

![select query image](/img/not.PNG);


### The SQL INSERT INTO Statement
The INSERT INTO statement is used to insert new records in a table.

#### INSERT INTO Syntax
It is possible to write the INSERT INTO statement in two ways:

1. Specify both the column names and the values to be inserted:

INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the INSERT INTO syntax would be as follows:

INSERT INTO table_name
VALUES (value1, value2, value3, ...);

### code for insert into 
 ` INSERT INTO employees VALUES(NULL,'Karim','karim@gmail.com','gender',4500,'Dhaka','Bangladesh');`

 ![select query image](/img/insert.PNG);

 ## What is a NULL Value?
 A field with a NULL value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

#### How to Test for NULL Values?
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

### code for is null 
`SELECT name, salary,country FROM employees where city IS NULL;`

![select query image](/img/is_null.PNG);

## code for is not null
`SELECT name, salary , country from employees WHERE city IS NOT null`

![select query image](/img/not_null.PNG);

## The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.

UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

# Note: 
Be careful when updating records in a table! Notice the WHERE clause in the UPDATE statement. The WHERE clause specifies which record(s) that should be updated. If you omit the WHERE clause, all records in the table will be updated!

## code for update
`UPDATE employees SET name="hello", city="Chittagong" WHERE id=7;`

![select query image](/img/update.PNG);

## The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.

# DELETE Syntax
DELETE FROM table_name WHERE condition;

# Note: 
Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!

## code for delete query
`DELETE FROM employees WHERE name="hello";`

## img
![select query image](/img/delete.PNG);

## The SQL MIN() and MAX() Functions
The MIN() function returns the smallest value of the selected column.

The MAX() function returns the largest value of the selected column.

# Syntax
SELECT MIN(column_name)
FROM table_name
WHERE condition;

SELECT MAX(column_name)
FROM table_name
WHERE condition;

## Set Column Name (Alias)
When you use MIN() or MAX(), the returned column will not have a descriptive name. To give the column a descriptive name, use the AS keyword:

## code for lowest salary
`SELECT MIN(salary) as lowest_employee_salary FROM employees;`

![select query image](/img/min_salary.PNG);

## code for highest/max salary 

`SELECT MAX(salary) as highest_employee_salary FROM employees;`

![select query image](/img/highest_salary.PNG);

## The SQL COUNT() Function
The COUNT() function returns the number of rows that matches a specified criterion.

## Syntax
SELECT COUNT(column_name)
FROM table_name
WHERE condition;

## code for count
`SELECT COUNT(name) FROM employees WHERE salary>5000;`
![select query image](/img/count.PNG);

## The SQL SUM() Function

The SUM() function returns the total sum of a numeric column.

## code for sum query
`SELECT SUM(salary) AS total_employee_salary FROM employees;`

![select query image](/img/sum.PNG);

## The SQL AVG() Function
The AVG() function returns the average value of a numeric column.

## code for avg query
`SELECT AVG(salary) as average_employee_salary FROM employees;`








