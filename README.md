<img width="844" height="957" alt="image" src="https://github.com/user-attachments/assets/d0de5ca0-df9f-48fc-be20-46a58a8d3e37" /># Oracle-SQL

[Agenda]
1. Introduction
2. Creation of Tables
3. Oracle setup and installation
4. Relational Model
5. Miscellaneous Topics
6. Operators as keywords
7. Functions
8. Clauses
9. Nested Query
10. SQL Commands
11. Database Objects and SP



**1. Introduction**

Database = Group of Information
>In 1960s, High level programming language developers suggested to make a use of programming languages to manage(store and retrive)the Facts and Figure.
>In programming language there is a concept called datatypes,variables and arrays. One can make a use of it and can store facts and figures.
>People were very happy because computers do not hava a disadvantage like LEDGERS, and now they have a why to store facts and figure in the computers and they did that using the programming language.
>But as the size of facts and the figure increased, programming languages failed to manage it.
>Programming language are successful only to manageing (Storeing and retriving) data (small volumns of facts and figures) but not database(Large volumn of facts and figure).


**DBMS(DATABASE MANAGEMENT SYSTEM)**
It is a software which is used to (manage)store data permanently and retrive the large amount of data efficiently.
for eg: Oracle, MySQL, DB2, Informix etc...

**2. Creation of Tables**
    1. Creation of Table:

      CREATE TABLE Student
      (
      ID number(10),
      Name varchar2(30),
      Age number,
      Gender varchar2(6),
      Marks number,
      SEM number
      );

    2. Now, Let's see how to insert the data into the table:

      INSERT INTO Student VALUES(52, 'AMAN', 26, 'MALE', 98, 8);
      INSERT INTO Student VALUES(52, 'MOHAN', 27, 'MALE', 94, 8);


**3. Oracle setup and installation**
git clone  https://github.com/oracle/docker-image

./buildContainerImage.sh -v 19.3. 0 -e

docker run -d --name oracle19 -e ORACLE_PWD=mypassword1 -p 1521:1521 oracle/database:19.3.0-ee 


rm -rf ~/Library/Application\ Support/Code
rm -rf ~/.vscode

https://code.visualstudio.com/


git config --global user.name "Anee"
git config --global user.email "thapaanita1111@gmail.com"


docker exec -it <container_name> bash
lsnrctl status




**4. Relational Model**

<img width="914" height="955" alt="image" src="https://github.com/user-attachments/assets/87e97e82-ea41-4a90-8edd-7a5d8316960d" />

    1. Relation = Table
    2. Tuple = A Row or a record in a relation
    3. Attribute = A feild or a column in a relation
    4. Cardinality of a relatuin = The number of tuple in a relation
    5. Degree of a relation = The number of attribute in a relaion
    6. Primary Key of a relation = An Attribute or a combination of atteributes that uniquely defines each tuple in a relation
    7. Foreign key = An Attribute or a combination of attributes in one relation R1 that indicates the relationship of R1 with another relation R2. The foreign kry attributes inR1 must contain values maching with those of the valuesin R2
     
**5. Miscellaneous Topics:**
  > Projection:
     Projection means choosing which columns (or expressions) the query shall return. Projection is the process of displaying the result using project queries. Project queries are all those queries which is used to display(project) particular columns  to the user based on the requirement from user. 
  >  Selection:
     Selection means which rows are to be returned. Selection is the process of displaying the result using select queries. Select queries are those queries which display particular rows to the users base on specific conditions.
  > Case Sensitivity in SQL:  
    The SQL keywords are case-insensitive (SELECT, FROM, WHERE, AS, ORDER BY, HAVING, GROUP BY, etc), but are usually written in all capitals.
            1. KEYWORDS IN SQL IS NOT CASE SENSITIVE.
            2. TABLE NAME IN SQL ARE NOT CASE SENSITIVE.
            3. COLUMN NAME IN SQL ARE NOT CASE SENSITIVE.
            4. DATA IN SQL IS CASE SENSITIVE.
<img width="1522" height="1005" alt="image" src="https://github.com/user-attachments/assets/c6779c2d-364a-49f2-bdd3-d2cdf02e9560" />
    > DataTypes:
        A data type specifies a particular types of data, such as integer, floating-point, Boolean etc. A data type also specifies the possibke values for that type, the operations that can be performed on that type and the way the values of that type are stored.
        *Oracle provides the following built-in datatype:
        - Character datatypes
                CHAR DATATYPE
                VARCHAR2 AND VARCHAR DATATYPES
                LONG DATATYPE
        - Number datatype
                FLOAT datatype
        - DATA Datatype

**6. Operators as keywords**
Operators:

🔹 What is SQL?
SQL (Structured Query Language) is a language used to communicate with relational databases. With SQL, you can:
<img width="414" height="608" alt="image" src="https://github.com/user-attachments/assets/e91e63cf-48ba-4e55-93f4-452e46d97583" />

🔹 What is a Table?
A table is like a spreadsheet. It has:
> Rows (each row = one record)
> Columns (each column = one field)
Example: employees table
<img width="714" height="221" alt="image" src="https://github.com/user-attachments/assets/1c3fb046-c000-46c3-829c-1bcf7d6e8a1e" />

🧠 SELECT Statement
✅ Purpose: To retrieve data from a table.
🔹 Basic Syntax:
🔹 Example:
This shows only the first_name and last_name columns from the employees table.


📘 Lesson 2: WHERE Clause in SQL
✅ Purpose: The WHERE clause is used to filter rows based on a condition. It helps you get only the data you need.
🔹 Syntax:
SELECT column1, column2
FROM table_name
WHERE condition;
🔹 Example 1:
SELECT first_name, salary
FROM employees
WHERE salary > 5000;
🔍 This query shows only employees whose salary is greater than 5000.

🔹 Example 2:
SELECT first_name, department_id
FROM employees
WHERE department_id = 10;

🔍 This shows employees who belong to department 10.

🔹 Common Operators Used in WHERE
<img width="508" height="683" alt="image" src="https://github.com/user-attachments/assets/8a07c6a7-2d60-44e0-b893-026a0b792602" />

📘 Lesson 3: Sorting Data with ORDER BY
✅ Purpose:
The ORDER BY clause is used to sort the results of a query in ascending or descending order.
ORDER BY is used to sort the result set from a SELECT query by one or more columns.

🔹 Basic Syntax:
sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC];
> ASC = Ascending order (default)
> DESC = Descending order

🔸 Example 1: Sort by one column
sql
SELECT * FROM employees
ORDER BY salary;
👉 This will list employees by salary from lowest to highest.

🔸 Example 2: Sort by one column (descending)
sql
SELECT * FROM employees
ORDER BY hire_date DESC;
👉 This will show most recently hired employees first.

🔸 Example 3: Sort by multiple columns
sql
SELECT * FROM employees
ORDER BY department_id ASC, salary DESC;
👉 First sorted by department_id (A→Z), then by salary (high→low) within each department.

🔸 Example 4: Using column position (not recommended, but valid)
sql
SELECT first_name, last_name, hire_date
FROM employees
ORDER BY 3 DESC;
👉 This sorts by the 3rd column, which is hire_date, in descending order.

🧠 Notes:
> ORDER BY comes last in the SQL query.
> You can sort by columns that are not selected in the SELECT clause (in Oracle).


🔷 What are SQL Functions?
SQL functions are built-in routines in Oracle that perform operations on data and return a value.
SQL functions allow you to transform or calculate values in your queries.

🔸 Types of SQL Functions in Oracle
Type
Description
Single-Row Functions
Return one result per row
Group Functions
Return one result for a group of rows


🔹 1. Single-Row Functions
✅ Purpose:Single-row functions operate on one row at a time and return one result per row.

These are applied to each row and return one result per row.
🧮 a. Number Functions
    > ROUND(n, m) – Rounds number n to m decimal places
        👉 ROUND(123.456, 2) → 123.46
    > TRUNC(n, m) – Truncates without rounding
        👉 TRUNC(123.456, 2) → 123.45
    > MOD(m, n) – Remainder of division
        👉 MOD(10, 3) → 1
🕒 b. Date Functions
    >  SYSDATE – Current date and time
    > MONTHS_BETWEEN(d1, d2) – Difference in months
    >  ADD_MONTHS(d, n) – Add months to a date
    > NEXT_DAY(d, 'FRIDAY') – Next Friday after d
🅰️ c. Character Functions
    > UPPER('anita') → ANITA
    > LOWER('ORACLE') → oracle
    > INITCAP('hello world') → Hello World
    > LENGTH('Anita') → 5
    SUBSTR('Oracle', 2, 3) → rac
🔍 d. Conversion Functions
    > TO_CHAR(date/number) – Convert to character
    > TO_DATE('2025-07-01', 'YYYY-MM-DD') – Convert to date
    > TO_NUMBER('100') – Convert to number

🔹 2. Group (Aggregate) Functions
These work on sets of rows and return a single result:
Function            Description
SUM()                Total sum
AVG()                Average
MAX()                Maximum value
MIN()                Minimum value
COUNT()              Count rows

sql
SELECT COUNT(*) FROM employees;
SELECT AVG(salary) FROM employees;

🧪 Example Query:
sql
SELECT department_id, COUNT(*), AVG(salary)
FROM employees
GROUP BY department_id;
This shows the number of employees and average salary per department.


✅ What is GROUP BY in Oracle?
The GROUP BY clause is used when you want to group rows that have the same value in a column — and then apply aggregate functions like COUNT(), SUM(), AVG(), etc., to each group.
Think of it like organizing data into groups — and then calculating something for each group.

🔹 Basic Syntax
sql
SELECT column_name, AGGREGATE_FUNCTION(column_name)
FROM table_name
GROUP BY column_name;
column_name is what you want to group by (like status or customer_id)
AGGREGATE_FUNCTION() is something like COUNT(), AVG(), etc.

🧾 Example Table: orders
<img width="733" height="289" alt="image" src="https://github.com/user-attachments/assets/3f94c224-aeeb-476f-8a9c-e256ba838c7b" />

🔸 Example 1: Group by status
sql
SELECT status
FROM orders
GROUP BY status;
👉 This will return:
Canceled
Pending
Shipped
Why? Because it groups rows by status. There are 3 statuses.

🔸 Example 2: Count orders by status
sql
SELECT status, COUNT(order_id) AS order_count
FROM orders
GROUP BY status;
👉 Output:
Canceled | 1
Pending  | 1
Shipped  | 3
📝 It shows how many orders are in each status.

🔸 Example 3: Count orders per customer
sql
SELECT customer_id, COUNT(order_id)
FROM orders
GROUP BY customer_id
ORDER BY customer_id;
👉 Groups by customer_id, and counts how many orders each customer made.

🔸 Example 4: Use JOIN + GROUP BY
If you want to get customer names instead of IDs:
sql
SELECT name, COUNT(order_id)
FROM orders
INNER JOIN customers USING (customer_id)
GROUP BY name
ORDER BY name;

🔸 Example 5: Group by Year
sql
SELECT EXTRACT(YEAR FROM order_date) AS order_year,
       COUNT(order_id) AS order_count
FROM orders
GROUP BY EXTRACT(YEAR FROM order_date)
ORDER BY order_year;
👉 This groups the orders by year and counts how many were made each year.

🔸 Example 6: Use WHERE + GROUP BY
sql
SELECT name, COUNT(order_id)
FROM orders
INNER JOIN customers USING (customer_id)
WHERE status = 'Shipped'
GROUP BY name
ORDER BY name;
👉 First filters only “Shipped” orders, then groups by customer name.

🔁 SQL Execution Order
Oracle processes the SQL query in this order:
1. FROM
2. WHERE
3. GROUP BY
4. HAVING (optional)
5. SELECT
6. ORDER BY
So you cannot use column aliases (like order_year) in the GROUP BY clause — you must repeat the full expression.

📝 Summary
✅ Use GROUP BY to:
    > Group rows with the same value
    > Use aggregate functions like COUNT(), AVG(), MAX(), SUM() on each group
✅ Combine GROUP BY with:
    > WHERE → to filter rows before grouping
    > ORDER BY → to sort the results
    > JOIN → to bring data from other tables
✅ What is the HAVING Clause in Oracle?
The HAVING clause is used when you want to filter grouped data — after using GROUP BY.
Think of it like this:
> WHERE filters rows
> HAVING filters groups

🔹 Syntax:
sql
SELECT column1, AGG_FUNCTION(column2)
FROM table_name
GROUP BY column1
HAVING condition;

🧾 Example Table: order_items
<img width="602" height="388" alt="image" src="https://github.com/user-attachments/assets/a2f75275-f59f-486a-a222-92f9ed23e74d" />

🔸 Example 1: Get Total Value per Order
sql
SELECT order_id, SUM(quantity * unit_price) AS total
FROM order_items
GROUP BY order_id;
🔍 This query gives the total value for each order.
Result:
order_id        total
7                29,267.81
11               39,687.59
20               90,695.37


🔸 Example 2: Use HAVING to Filter Orders Over 30,000
sql
SELECT order_id, SUM(quantity * unit_price) AS total
FROM order_items
GROUP BY order_id
HAVING SUM(quantity * unit_price) > 30000;
🔍 This shows only orders with total value over 30,000.
Result:
order_id        total
11                39,687.59
20                90,695.37


🧠 Quick Reminder
Clause            What it filters        When it's used
WHERE             Filters rows          Before GROUP BY
HAVING            Filters groups        After GROUP BY


🔸 Example 3: Orders over 1,000,000
sql
SELECT order_id, SUM(unit_price * quantity) AS order_value
FROM order_items
GROUP BY order_id
HAVING SUM(unit_price * quantity) > 1000000
ORDER BY order_value DESC;
🔍 Shows only very large orders with total value over 1 million.

🔸 Example 4: Complex HAVING Conditions
Let’s say you want orders that:
    > Have a total value over 500,000, and
    > Have between 10 and 12 products in the order
sql
SELECT order_id,
       COUNT(item_id) AS item_count,
       SUM(unit_price * quantity) AS total
FROM order_items
GROUP BY order_id
HAVING SUM(unit_price * quantity) > 500000
  AND COUNT(item_id) BETWEEN 10 AND 12
ORDER BY total DESC, item_count DESC;

✅ Summary (Super Easy Version):
🔹                                    ✅
Use GROUP BY                    To group rows by column
Use HAVING                      To filter grouped results
Use aggregate functions         Like SUM(), COUNT(), AVG() with HAVING
HAVING ≠ WHERE                  HAVING is for groups, WHERE is for rows



✅ What is a JOIN in SQL?
A JOIN is used to combine data from two or more tables based on a related column (usually a primary key and a foreign key).
For example:
You might have a customers table and an orders table — and want to see which customer placed which order.

🔹 Basic Types of JOINS in Oracle
Join Type                Description
INNER JOIN            Returns only rows that have matching values in both tables
LEFT JOIN             Returns all rows from the left table, and matched rows from the right
RIGHT JOIN            Returns all rows from the right table, and matched rows from the left
FULL JOIN             Returns all rows when there is a match in either table
CROSS JOIN            Returns all possible combinations (Cartesian Product)


🔸 1. INNER JOIN (most common)
sql
SELECT c.customer_id, c.name, o.order_id
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id;
🔍 Only returns rows where customer_id exists in both customers and orders.

🔸 2. LEFT OUTER JOIN
sql
SELECT c.customer_id, c.name, o.order_id
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id;
🔍 Returns all customers, even if they didn’t place any orders.
Unmatched order_id will be NULL.

🔸 3. RIGHT OUTER JOIN
sql
SELECT c.customer_id, c.name, o.order_id
FROM customers c
RIGHT JOIN orders o
ON c.customer_id = o.customer_id;
🔍 Returns all orders, even if there is no matching customer (rare but possible in bad data).

🔸 4. FULL OUTER JOIN
sql
SELECT c.customer_id, c.name, o.order_id
FROM customers c
FULL OUTER JOIN orders o
ON c.customer_id = o.customer_id;
🔍 Returns everything — all customers and all orders, with NULLs where there are no matches.

🔸 5. CROSS JOIN
sql
SELECT c.name, p.product_name
FROM customers c
CROSS JOIN products p;
🔍 Every customer will be matched with every product. (Use this with caution — can create huge result sets.)

🧠 Visualization of JOIN Types:
JOIN Type            Example Output
INNER JOIN           Only matching rows (A ∩ B)
LEFT JOIN            All from left + matches from right (A ⟶ B)
RIGHT JOIN           All from right + matches from left (A ⟵ B)
FULL JOIN            All from both sides (A ∪ B)


✅ Summary
Clause            Purpose
JOIN            Combine rows from two tables
ON              Defines how the tables are related
INNER JOIN      Matching rows only
LEFT JOIN       All left + matched right rows
RIGHT JOIN      All right + matched left rows
FULL JOIN       All rows from both sides



✅ What Are Set Operators in Oracle SQL?
Set operators allow you to combine the result sets of two or more SELECT statements.

🔹 Main Set Operators in Oracle:
Operator            Description
UNION               Combines results without duplicates
UNION ALL           Combines results with duplicates
INTERSECT           Shows only common rows in both queries
MINUS               Shows rows in the first query only


🔸 1. UNION
sql
SELECT name FROM customers
UNION
SELECT name FROM employees;
✅ Combines both lists, removes duplicates
✅ Sorts results by default

🔸 2. UNION ALL
sql
SELECT name FROM customers
UNION ALL
SELECT name FROM employees;
✅ Combines both lists including duplicates
✅ Faster than UNION (because no sorting or checking)

🔸 3. INTERSECT
sql
SELECT customer_id FROM orders
INTERSECT
SELECT customer_id FROM customers;
✅ Returns only the common customer IDs in both queries.

🔸 4. MINUS
sql
SELECT customer_id FROM customers
MINUS
SELECT customer_id FROM orders;
✅ Returns customer IDs that exist in customers but not in orders

🔸 Important Rules
    > Each SELECT must have the same number of columns
    > Columns must be of compatible data types
    > Column names are taken from the first SELECT query
    > Set operators ignore ORDER BY unless used at the end
✅ Example with ORDER BY:
sql
SELECT name FROM customers
UNION
SELECT name FROM employees
ORDER BY name;

📝 Summary Table
Operator        Keeps Duplicates?        Orders Automatically?        Purpose
UNION            ❌ No                    ✅ Yes                    Combine, remove duplicates
UNION ALL        ✅ Yes                   ❌ No                     Combine, keep duplicates
INTERSECT        ❌ No                    ❌ No                     Common rows only
MINUS            ❌ No                    ❌ No                     Rows from first query, not second



🔍 What Is a Subquery?
A subquery (also called an inner query or nested query) is a query embedded inside another SQL query. It allows you to use the result of one query as input for another.
Subqueries are often used in:
        > SELECT statements
        > WHERE clauses
        > FROM clauses
        > HAVING clauses

🧠 Basic Structure

📘 Example 1: Subquery in WHERE Clause
This query finds all employees who work in the Sales department.

📘 Example 2: Subquery in SELECT Clause
This adds a column showing the average salary for all employees.

📘 Example 3: Subquery in FROM Clause
This finds departments where the average salary is greater than $50,000.

✅ Tips for Using Subqueries
    > Subqueries must be enclosed in parentheses ().
    > You can use single-row or multi-row subqueries depending on the context.
    > Use operators like =, IN, ANY, ALL, EXISTS with subqueries.


















































