Welcome to your 90-minute gym interview session.
Today we are focusing mainly on SQL and ETL, followed by Java, testing, Selenium and DSA.
You do not need to speak.
You do not need to answer me verbally.
You do not need to stop your workout.
Simply listen.
For every ## question, try to answer mentally before the answer is revealed.
If you know the answer, say it in your head.
If you do not know the answer, think about what you would say in an interview.
Then listen to the answer and explanation.
The goal is not memorization.
The goal is to train your interview thinking.
Let's begin.
[break:3s]
PART 1.
SQL.
This is the most important section of today's session.
We will start with fundamentals and gradually move toward difficult interview ## questions, SQL queries, tricky scenarios, and real-world problems.
[break:3s]
## question 1.
What is SQL?
Think about your answer now.
[break:8s]
Answer.
SQL stands for Structured Query Language.
It is used to communicate with relational databases.
We use SQL to retrieve, insert, update, delete, and manipulate data.
We can also use SQL to create and modify database structures.
Explanation.
Do not confuse SQL with MySQL.
SQL is the language.
MySQL is a database management system that supports SQL.
[break:3s]
## question 2.
What is the difference between DDL, DML and TCL?
Think now.
[break:10s]
Answer.
DDL means Data Definition Language.
It deals mainly with database structures.
Examples are CREATE, ALTER, TRUNCATE and DROP.
DML means Data Manipulation Language.
Examples are INSERT, UPDATE and DELETE.
TCL means Transaction Control Language.
Examples are COMMIT, ROLLBACK and SAVEPOINT.
There is also DQL, commonly used for SELECT.
Explanation.
A simple way to remember this is:
DDL changes structure.
DML changes data.
TCL controls transactions.
[break:3s]
## question 3.
What is the difference between DELETE, TRUNCATE and DROP?
Think carefully.
[break:10s]
Answer.
DELETE removes rows from a table.
TRUNCATE removes all rows while keeping the table structure.
DROP removes the table itself.
DELETE can normally use a WHERE condition.
For example:
DELETE FROM employees WHERE department_id = 10;
TRUNCATE removes all rows.
DROP removes the table.
Explanation.
The exact transaction behavior can differ between database systems, so when an interviewer specifies MySQL, Oracle, SQL Server or PostgreSQL, answer according to that database.
[break:3s]
## question 4.
What is a primary key?
Think now.
[break:7s]
Answer.
A primary key uniquely identifies a row in a table.
It cannot contain NULL values.
A table normally has one primary key constraint.
That primary key can contain multiple columns.
That is called a composite primary key.
[break:3s]
## question 5.
What is a foreign key?
Think now.
[break:7s]
Answer.
A foreign key is a column or group of columns that references a key in another table.
It helps maintain referential integrity.
For example, employees may contain department_id that references department_id in departments.
[break:3s]
## question 6.
What is the difference between primary key and UNIQUE?
Think now.
[break:10s]
Answer.
Both can enforce uniqueness.
A primary key identifies the main key of the table and cannot contain NULL.
A table can have multiple UNIQUE constraints.
NULL behavior for UNIQUE constraints depends on the database system.
In MySQL, a UNIQUE index can permit multiple NULL values.
[break:3s]
## question 7.
What is NULL?
Think now.
[break:7s]
Answer.
NULL represents a missing, unknown or unavailable value.
NULL is not the same as zero.
NULL is not the same concept as an ordinary empty string.
To check for NULL, use IS NULL.
To check for non-NULL values, use IS NOT NULL.
[break:3s]
## question 8.
What happens if you write:
WHERE manager_id = NULL?
Think carefully.
[break:8s]
Answer.
It does not correctly identify NULL values.
You should write:
WHERE manager_id IS NULL.
Explanation.
NULL uses SQL's three-valued logic.
Comparisons with NULL can produce UNKNOWN rather than TRUE.
This is one of the most common SQL interview traps.
[break:3s]
## question 9.
What is the difference between WHERE and HAVING?
Think now.
[break:10s]
Answer.
WHERE filters individual rows before grouping.
HAVING filters groups after GROUP BY.
For example:
SELECT department_id, COUNT()
FROM employees
WHERE salary > 30000
GROUP BY department_id
HAVING COUNT() > 5;
Explanation.
WHERE first removes employees whose salary does not meet the condition.
GROUP BY creates department groups.
HAVING then filters those groups.
[break:3s]
## question 10.
What is DISTINCT?
Think now.
[break:6s]
Answer.
DISTINCT removes duplicate combinations from the query result.
For example:
SELECT DISTINCT department_id
FROM employees;
This returns each department only once.
Important point.
DISTINCT does not delete duplicate data from the table.
It only changes the query result.
[break:3s]
## question 11.
What is ORDER BY?
Think now.
[break:5s]
Answer.
ORDER BY sorts the query result.
For example:
SELECT *
FROM employees
ORDER BY salary DESC;
DESC means descending.
ASC means ascending.
[break:3s]
## question 12.
What are aggregate functions?
Think now.
[break:7s]
Answer.
Aggregate functions calculate a result across multiple rows.
Common aggregate functions are:
COUNT.
SUM.
AVG.
MIN.
MAX.
[break:3s]
## question 13.
What is the difference between COUNT star and COUNT column?
Think carefully.
[break:10s]
Answer.
COUNT star counts rows.
COUNT of a specific column counts non-NULL values in that column.
Suppose salary contains:
10000.	
10001.	
NULL.
30000.	
NULL.
COUNT star returns five.
COUNT salary returns three.
[break:3s]
## question 14.
Write a query to find the number of employees in each department.
Think about the query.
[break:15s]
Answer.
SELECT department_id, COUNT(*) AS employee_count
FROM employees
GROUP BY department_id;
Explanation.
GROUP BY creates one group for every department.
COUNT counts the rows in each group.
[break:3s]
## question 15.
Write a query to find departments having more than five employees.
Think now.
[break:15s]
Answer.
SELECT department_id, COUNT() AS employee_count
FROM employees
GROUP BY department_id
HAVING COUNT() > 5;
Explanation.
Because COUNT is an aggregate condition, we use HAVING.
[break:3s]
## question 16.
What is an INNER JOIN?
Think now.
[break:7s]
Answer.
INNER JOIN returns rows where the join condition matches in both tables.
[break:3s]
## question 17.
What is a LEFT JOIN?
Think now.
[break:7s]
Answer.
LEFT JOIN returns every row from the left table and matching rows from the right table.
If there is no match, right-side columns become NULL.
[break:3s]
## question 18.
What is a RIGHT JOIN?
Think now.
[break:6s]
Answer.
RIGHT JOIN returns every row from the right table and matching rows from the left table.
If there is no match, left-side columns become NULL.
[break:3s]
## question 19.
What is a FULL OUTER JOIN?
Think now.
[break:7s]
Answer.
A FULL OUTER JOIN returns matching rows plus unmatched rows from both sides.
Where there is no match, the columns from the other side contain NULL.
Some database systems do not support FULL OUTER JOIN directly and may require another approach such as UNION.
[break:3s]
## question 20.
What is a CROSS JOIN?
Think now.
[break:7s]
Answer.
CROSS JOIN creates a Cartesian product.
Every row from the first table is combined with every row from the second table.
If the first table has ten rows and the second has five rows, the result can contain fifty rows.
[break:3s]
## question 21.
What is a SELF JOIN?
Think now.
[break:7s]
Answer.
A SELF JOIN means joining a table to itself.
It is useful when rows in the same table have relationships with one another.
A classic example is employees and managers.
[break:3s]
## question 22.
How would you display an employee's name and manager's name?
Think about the query.
[break:15s]
Answer.
SELECT e.name AS employee,
m.name AS manager
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.employee_id;
Explanation.
The first copy of the employees table represents the employee.
The second copy represents the manager.
This is a SELF JOIN.
[break:3s]
## question 23.
How would you find employees who do not have a department?
Think for fifteen seconds.
[break:15s]
Answer.
SELECT e.*
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id
WHERE d.department_id IS NULL;
Explanation.
The LEFT JOIN keeps all employees.
Employees without a matching department receive NULL department values.
The WHERE condition keeps those employees.
[break:3s]
## question 24.
What happens if you forget the JOIN condition?
Think carefully.
[break:8s]
Answer.
You may accidentally create a Cartesian product.
That can produce far more rows than expected.
One of the first things to investigate when a join suddenly increases row count is whether the join condition is missing or incomplete.
[break:3s]
## question 25.
Suppose employees has 100 rows and departments has 10 rows.
How many rows could a CROSS JOIN produce?
Think now.
[break:6s]
Answer.
100 multiplied by 10.
That is 1,000 rows.
[break:3s]
## question 26.
What is a subquery?
Think now.
[break:6s]
Answer.
A subquery is a query inside another query.
It can appear in places such as WHERE, FROM, or SELECT depending on the query.
[break:3s]
## question 27.
What is a single-row subquery?
Think now.
[break:6s]
Answer.
A single-row subquery returns one value or one row that can be used by the outer query where a single result is expected.
[break:3s]
## question 28.
How would you find employees earning more than the average salary?
Think about the SQL.
[break:15s]
Answer.
SELECT *
FROM employees
WHERE salary >
(SELECT AVG(salary)
FROM employees);
Explanation.
The inner query calculates the average salary.
The outer query compares each employee's salary with that average.
[break:3s]
## question 29.
What is a multiple-row subquery?
Think now.
[break:7s]
Answer.
A multiple-row subquery returns multiple values.
Operators such as IN, ANY or ALL can be used depending on the requirement.
[break:3s]
## question 30.
What is a correlated subquery?
Think carefully.
[break:10s]
Answer.
A correlated subquery depends on the outer query.
The inner query references a value from the current row of the outer query.
For example, finding employees whose salary is higher than the average salary of their own department.
[break:3s]
## question 31.
What is EXISTS?
Think now.
[break:7s]
Answer.
EXISTS checks whether a subquery returns at least one row.
It is mainly concerned with whether matching data exists.
[break:3s]
## question 32.
What is the difference between IN and EXISTS?
Think carefully.
[break:10s]
Answer.
IN compares a value against values returned by a subquery.
EXISTS checks whether at least one matching row exists.
Both can sometimes solve the same requirement.
The best choice depends on the query and database optimizer.
[break:3s]
Interviewer's follow-up.
Why can NOT IN be dangerous when NULL is involved?
Think carefully.
[break:12s]
Answer.
If the subquery contains NULL, SQL's three-valued logic can make comparisons evaluate to UNKNOWN.
This can produce unexpected results.
NOT EXISTS is often safer when NULL values may exist.
[break:3s]
## question 33.
What is COALESCE?
Think now.
[break:7s]
Answer.
COALESCE returns the first non-NULL expression.
For example:
COALESCE(phone_number, 'Not Available')
If phone_number is NULL, the result is Not Available.
[break:3s]
## question 34.
What is CASE?
Think now.
[break:6s]
Answer.
CASE provides conditional logic inside SQL.
For example:
CASE
WHEN salary >= 100000 THEN 'High'
WHEN salary >= 50000 THEN 'Medium'
ELSE 'Low'
END
It can classify or transform values according to conditions.
[break:3s]
## question 35.
What is CAST?
Think now.
[break:6s]
Answer.
CAST converts a value from one data type to another.
The exact syntax and supported conversions depend on the database system.
[break:3s]
## question 36.
Name some common string functions.
Think now.
[break:7s]
Answer.
UPPER.
LOWER.
LENGTH.
SUBSTRING.
TRIM.
CONCAT.
REPLACE.
The exact functions can differ between database systems.
[break:3s]
## question 37.
Why should you be careful with date functions during an interview?
Think now.
[break:8s]
Answer.
Because date syntax differs between databases.
MySQL, Oracle, SQL Server and PostgreSQL do not always use the same functions.
If the interviewer specifies the database, use that database's syntax.
[break:3s]
## question 38.
Find the second-highest salary.
Think for fifteen seconds.
[break:15s]
Answer.
One approach is:
SELECT MAX(salary)
FROM employees
WHERE salary <
(SELECT MAX(salary)
FROM employees);
Explanation.
The inner query finds the highest salary.
The outer query finds the maximum salary below that value.
This gives the second distinct salary.
[break:3s]
## question 39.
What is the difference between second-highest salary and second row after sorting?
Think carefully.
[break:10s]
Answer.
Second-highest salary usually means the second distinct salary value.
Second row means the second row after sorting.
If multiple employees have the same highest salary, the results can be different.
Always understand the exact requirement.
[break:3s]
## question 40.
What is ROW_NUMBER?
Think now.
[break:6s]
Answer.
ROW_NUMBER assigns a unique sequential number to each row within the window.
[break:3s]
## question 41.
What is RANK?
Think now.
[break:6s]
Answer.
RANK assigns the same rank to tied values and leaves gaps after the tie.
[break:3s]
## question 42.
What is DENSE_RANK?
Think now.
[break:6s]
Answer.
DENSE_RANK gives tied values the same rank but does not leave gaps.
[break:3s]
## question 43.
Suppose salaries are 100, 100 and 90.
What are the RANK values?
Think now.
[break:7s]
Answer.
One.
One.
Three.
[break:3s]
## question 44.
What are the DENSE_RANK values?
Think now.
[break:7s]
Answer.
One.
One.
Two.
[break:3s]
## question 45.
What is PARTITION BY?
Think now.
[break:7s]
Answer.
PARTITION BY divides rows into logical groups for a window function.
For example:
ROW_NUMBER() OVER
(
PARTITION BY department_id
ORDER BY salary DESC
)
This numbers employees separately within each department.
[break:3s]
## question 46.
Find the highest-paid employee in each department.
Think for twenty seconds.
[break:20s]
Answer.
One approach is:
SELECT *
FROM
(
SELECT e.*,
ROW_NUMBER() OVER
(
PARTITION BY department_id
ORDER BY salary DESC
) AS rn
FROM employees e
) x
WHERE rn = 1;
Explanation.
Employees are divided by department.
Within each department they are sorted by salary.
The highest salary gets row number one.
Then the outer query keeps row number one.
[break:3s]
## question 47.
What happens if two employees are tied for the highest salary?
Think now.
[break:8s]
Answer.
ROW_NUMBER will still give them different numbers.
Only one will receive number one.
If you want all employees tied for the highest salary, RANK or DENSE_RANK can be more appropriate.
[break:3s]
## question 48.
Write a query to find duplicate email addresses.
Think for fifteen seconds.
[break:15s]
Answer.
SELECT email, COUNT() AS cnt
FROM customers
GROUP BY email
HAVING COUNT() > 1;
Explanation.
GROUP BY creates one group for each email.
HAVING keeps groups containing more than one row.
[break:3s]
## question 49.
How would you find duplicate records based on name, email and phone?
Think now.
[break:15s]
Answer.
SELECT name, email, phone, COUNT()
FROM customers
GROUP BY name, email, phone
HAVING COUNT() > 1;
The important point is that the business definition of a duplicate determines which columns you group by.
[break:3s]
## question 50.
Find the Nth-highest salary using DENSE_RANK.
Think for twenty seconds.
[break:20s]
Answer.
SELECT *
FROM
(
SELECT e.*,
DENSE_RANK() OVER
(
ORDER BY salary DESC
) AS rnk
FROM employees e
) x
WHERE rnk = N;
Explanation.
DENSE_RANK is useful when the requirement means the Nth distinct salary.
[break:3s]
## question 51.
Find the third row after sorting employees by salary descending.
Think for fifteen seconds.
[break:15s]
Answer.
SELECT *
FROM
(
SELECT e.*,
ROW_NUMBER() OVER
(
ORDER BY salary DESC
) AS rn
FROM employees e
) x
WHERE rn = 3;
The key is understanding whether the interviewer wants the Nth row or the Nth distinct salary.
[break:3s]
## question 52.
Find employees earning more than their managers.
Think for twenty seconds.
[break:20s]
Answer.
SELECT e.name AS employee,
e.salary AS employee_salary,
m.name AS manager,
m.salary AS manager_salary
FROM employees e
JOIN employees m
ON e.manager_id = m.employee_id
WHERE e.salary > m.salary;
Explanation.
This uses a SELF JOIN.
One copy represents employees.
The other represents managers.
Then we compare salaries.
[break:3s]
## question 53.
What is a CTE?
Think now.
[break:7s]
Answer.
CTE means Common Table Expression.
It is created using WITH.
It gives a temporary named result that can be referenced by the main query.
For example:
WITH high_salary AS
(
SELECT *
FROM employees
WHERE salary > 50000
)
SELECT *
FROM high_salary;
[break:3s]
## question 54.
Why can a CTE be useful?
Think now.
[break:7s]
Answer.
It can make complex SQL easier to read and maintain.
It lets you break a complex problem into logical steps.
Do not automatically claim that a CTE is faster than a subquery.
Performance depends on the database and execution plan.
[break:3s]
## question 55.
What is an index?
Think now.
[break:7s]
Answer.
An index is a data structure that can help the database locate rows more efficiently.
Indexes can improve certain read queries.
But they consume storage and can add overhead to INSERT, UPDATE and DELETE operations.
[break:3s]
## question 56.
If indexes improve SELECT performance, why not create indexes on every column?
Think carefully.
[break:10s]
Answer.
Because indexes have costs.
They consume storage.
They require maintenance.
They can slow down data modification operations.
Therefore, indexes should be created according to actual query patterns and performance requirements.
[break:3s]
## question 57.
What is a clustered index conceptually?
Think now.
[break:8s]
Answer.
A clustered index determines how table data is organized according to the database's storage model.
The exact implementation depends on the database.
For example, SQL Server allows one clustered index on a table because the data rows are organized according to that index.
Do not assume every database implements clustering identically.
[break:3s]
## question 58.
What is a non-clustered index?
Think now.
[break:7s]
Answer.
A non-clustered index is a separate index structure containing indexed values and references to the corresponding rows.
A table can have multiple non-clustered indexes depending on the database system.
[break:3s]
## question 59.
What is a view?
Think now.
[break:7s]
Answer.
A view is a stored query that can be queried like a virtual table.
It can simplify complex queries and can help control access to data.
[break:3s]
## question 60.
What is a stored procedure?
Think now.
[break:7s]
Answer.
A stored procedure is a named program stored in the database.
It can contain SQL statements and procedural logic supported by that database.
It can accept parameters and perform operations.
[break:3s]
## question 61.
What is a transaction?
Think now.
[break:7s]
Answer.
A transaction is a logical unit of database work.
The classic properties are ACID.
Atomicity.
Consistency.
Isolation.
Durability.
[break:3s]
## question 62.
What is COMMIT?
Think now.
[break:5s]
Answer.
COMMIT makes the transaction's changes permanent according to the database's transaction model.
[break:3s]
## question 63.
What is ROLLBACK?
Think now.
[break:5s]
Answer.
ROLLBACK reverses uncommitted transaction changes.
[break:3s]
## question 64.
What is SAVEPOINT?
Think now.
[break:5s]
Answer.
SAVEPOINT creates a point within a transaction to which you can roll back without necessarily rolling back the entire transaction.
[break:3s]
## question 65.
Real interview scenario.
Yesterday an ETL job loaded ten million rows.
Today it loaded twelve million.
The business expected approximately the same volume.
What would you investigate?
Think carefully.
[break:15s]
Answer.
First, verify the source row count.
Then check the extraction date range.
Check whether the same period was processed.
Check for duplicate records.
Check incremental-load conditions.
Check whether a join introduced duplicate rows.
Check whether the source itself contains more data.
Check transformation logic.
Check whether a previous failed load was reprocessed.
Finally, compare source and target counts and review the ETL logs.
Do not immediately assume the database is wrong.
First find where the difference was introduced.
[break:3s]
That completes the major SQL section.
Now we move into ETL and data testing.
[break:4s]
PART 2.
ETL AND DATA.
This section is extremely important for SQL and ETL-oriented interviews.
[break:3s]
## question 66.
What is ETL?
Think now.
[break:7s]
Answer.
ETL means Extract, Transform, Load.
Extract means obtaining data from source systems.
Transform means applying business rules, cleansing data, changing formats, joining data, filtering data or deriving new values.
Load means writing the processed data into the target system.
[break:3s]
## question 67.
What is the difference between ETL and ELT?
Think now.
[break:9s]
Answer.
In ETL, transformation generally happens before loading into the target.
In ELT, data is loaded into the target first and transformation happens there.
The appropriate architecture depends on the technology, data volume, requirements and environment.
[break:3s]
## question 68.
What is a source system?
Think now.
[break:6s]
Answer.
A source system is where the original data comes from.
Examples include operational databases, applications, APIs, files and external systems.
[break:3s]
## question 69.
What is a target system?
Think now.
[break:6s]
Answer.
A target system is where the processed data is loaded.
For example, a data warehouse or reporting database.
[break:3s]
## question 70.
What is source-to-target validation?
Think now.
[break:8s]
Answer.
Source-to-target validation checks whether data has been transferred and transformed correctly according to the defined mapping and business rules.
It can include row counts, column values, data types, transformations, NULL handling and business rules.
[break:3s]
## question 71.
The source contains one hundred thousand rows.
The target contains ninety-nine thousand five hundred rows.
Is this automatically a defect?
Think carefully.
[break:12s]
Answer.
No.
First check whether the difference is expected.
There could be filtering.
Rejected records.
Duplicate handling.
Incremental-load logic.
Invalid records.
Or different business rules.
The important ## question is why the five hundred rows are missing.
[break:3s]
## question 72.
What is row-count validation?
Think now.
[break:6s]
Answer.
Row-count validation compares the number of records between source and target or between different stages of the pipeline.
But matching row counts do not prove that the data is correct.
[break:3s]
## question 73.
How would you check for duplicate customer IDs?
Think now.
[break:10s]
Answer.
SELECT customer_id, COUNT()
FROM customers
GROUP BY customer_id
HAVING COUNT() > 1;
This identifies customer IDs appearing more than once.
[break:3s]
## question 74.
How would you check for NULL values in a mandatory column?
Think now.
[break:8s]
Answer.
SELECT COUNT(*)
FROM customers
WHERE customer_id IS NULL;
If customer_id is mandatory, the expected result may be zero.
[break:3s]
## question 75.
What is data reconciliation?
Think now.
[break:7s]
Answer.
Data reconciliation means comparing data between systems or processing stages to verify that information has been transferred correctly.
It can include row counts, totals, keys, individual records and business-level aggregates.
[break:3s]
## question 76.
Source sales total is fifty million.
Target sales total is forty-eight million.
What would you investigate?
Think carefully.
[break:12s]
Answer.
First check that both systems use the same date range.
Then check currency conversion.
Check filtering.
Check rejected records.
Check duplicate handling.
Check transformation logic.
Check missing records.
Check whether some records were intentionally excluded.
Then compare smaller groups to locate where the difference occurs.
[break:3s]
## question 77.
What is a full load?
Think now.
[break:6s]
Answer.
A full load processes the complete required dataset rather than only new or changed records.
[break:3s]
## question 78.
What is an incremental load?
Think now.
[break:6s]
Answer.
An incremental load processes only new or changed data since a previous processing point.
It can use timestamps, change flags, sequence numbers, CDC mechanisms or other business rules.
[break:3s]
## question 79.
What is SCD?
Think now.
[break:6s]
Answer.
SCD means Slowly Changing Dimension.
It describes techniques for handling changes in dimension data over time.
[break:3s]
## question 80.
Explain SCD Type 1.
Think now.
[break:7s]
Answer.
Type 1 overwrites the old value with the new value.
Historical values are not preserved.
For example, if a customer's city changes from Chennai to Bangalore, the existing value becomes Bangalore.
[break:3s]
## question 81.
Explain SCD Type 2.
Think now.
[break:8s]
Answer.
Type 2 preserves history by creating a new version of the record.
A common design uses a surrogate key, effective start date, effective end date and sometimes a current-record flag.
The old record remains available for historical reporting.
[break:3s]
## question 82.
An employee moves from Finance to HR.
The business wants historical reports to show Finance before the transfer and HR after the transfer.
Which SCD approach would you consider?
Think now.
[break:7s]
Answer.
SCD Type 2.
Because the business wants to preserve historical versions.
[break:3s]
## question 83.
What is a fact table?
Think now.
[break:6s]
Answer.
A fact table generally contains measurable business events or metrics.
Examples include sales amount, quantity, transaction count and revenue.
[break:3s]
## question 84.
What is a dimension table?
Think now.
[break:6s]
Answer.
A dimension table contains descriptive information used to analyze facts.
Examples include customer, product, employee, location and date.
[break:3s]
## question 85.
You are testing an ETL pipeline.
What validations would you perform?
Think now.
[break:12s]
Answer.
I would validate:
Source data.
Target data.
Row counts.
Data types.
NULL values.
Duplicates.
Business rules.
Transformation logic.
Joins.
Filters.
Aggregations.
Default values.
Rejected records.
And reconciliation.
[break:3s]
## question 86.
An ETL job fails halfway through processing.
What would you investigate?
Think carefully.
[break:12s]
Answer.
Where did it fail?
Which records were processed?
Was anything committed?
Was the target partially loaded?
Can the job safely restart?
Will restarting create duplicates?
Is the process idempotent?
What do the logs show?
Was there a source problem?
A schema problem?
A connection problem?
Or a transformation problem?
[break:3s]
## question 87.
What is data quality?
Think now.
[break:7s]
Answer.
Data quality describes whether data is suitable and reliable for its intended purpose.
Common dimensions include accuracy, completeness, consistency, validity, uniqueness and timeliness.
[break:3s]
## question 88.
Suppose a customer table has duplicate customer IDs, NULL email addresses and invalid phone numbers.
What type of problem is this?
Think now.
[break:7s]
Answer.
These are data-quality problems.
Duplicate IDs relate to uniqueness.
NULL mandatory emails relate to completeness.
Invalid phone numbers relate to validity.
[break:3s]
## question 89.
What SQL skills are particularly useful for ETL testing?
Think now.
[break:8s]
Answer.
Joins.
Aggregations.
GROUP BY.
HAVING.
Subqueries.
CTEs.
Window functions.
CASE.
NULL handling.
Duplicate detection.
Data reconciliation.
And source-to-target comparisons.
[break:3s]
That completes the ETL section.
Now we move into Java.
[break:4s]
PART 3.
JAVA.
[break:3s]
## question 90.
What are the four major principles of object-oriented programming?
Think now.
[break:7s]
Answer.
Encapsulation.
Inheritance.
Polymorphism.
Abstraction.
[break:3s]
## question 91.
What is encapsulation?
Think now.
[break:6s]
Answer.
Encapsulation means combining data and behavior together while controlling access to internal state.
Private fields with controlled access through methods are a common example.
[break:3s]
## question 92.
What is inheritance?
Think now.
[break:6s]
Answer.
Inheritance allows one class to acquire properties and behavior from another class.
It represents an IS-A relationship.
For example, Dog can extend Animal.
[break:3s]
## question 93.
What is polymorphism?
Think now.
[break:7s]
Answer.
Polymorphism allows one interface or reference to represent different implementations.
Method overloading is commonly described as compile-time polymorphism.
Method overriding supports runtime polymorphism.
[break:3s]
## question 94.
What is method overloading?
Think now.
[break:6s]
Answer.
Overloading means methods have the same name but different parameter lists.
It is resolved at compile time.
[break:3s]
## question 95.
What is method overriding?
Think now.
[break:6s]
Answer.
Overriding happens when a subclass provides its own implementation of an inherited method with the appropriate signature.
It supports runtime polymorphism.
[break:3s]
## question 96.
What is the difference between an interface and an abstract class?
Think carefully.
[break:10s]
Answer.
An abstract class can contain instance state, constructors, concrete methods and abstract methods.
An interface primarily defines a contract, although modern Java interfaces can contain default and static methods.
A class can implement multiple interfaces.
Java does not allow a class to extend multiple classes.
[break:3s]
## question 97.
What is the difference between String and StringBuilder?
Think now.
[break:8s]
Answer.
String is immutable.
StringBuilder is mutable.
StringBuilder is useful when repeatedly modifying or constructing strings.
[break:3s]
## question 98.
What is StringBuffer?
Think now.
[break:6s]
Answer.
StringBuffer is mutable and provides synchronized methods.
StringBuilder is generally preferred when synchronization is not required.
[break:3s]
## question 99.
What is the difference between double equals and equals?
Think carefully.
[break:10s]
Answer.
For objects, double equals compares references.
The equals method is used for logical equality when the class implements it appropriately.
For example, two different String objects can contain the same text and equals can consider them equal.
[break:3s]
## question 100.
Why is String comparison using double equals a common mistake?
Think now.
[break:7s]
Answer.
Because double equals may compare object references instead of string content.
For string content comparison, equals is normally used.
[break:3s]
## question 101.
What is the difference between List, Set and Map?
Think now.
[break:8s]
Answer.
List stores ordered elements and generally allows duplicates.
Set stores unique elements.
Map stores key-value pairs.
[break:3s]
## question 102.
What is ArrayList?
Think now.
[break:6s]
Answer.
ArrayList is a List implementation backed by a dynamically resizable array.
It provides fast random access by index.
[break:3s]
## question 103.
What is LinkedList?
Think now.
[break:6s]
Answer.
LinkedList is a linked data structure.
It can be useful for certain insertion and removal patterns.
But do not automatically assume it is faster than ArrayList.
[break:3s]
## question 104.
What is HashSet?
Think now.
[break:6s]
Answer.
HashSet stores unique elements.
It uses hashing internally.
It does not guarantee sorted order.
[break:3s]
## question 105.
What is HashMap?
Think now.
[break:6s]
Answer.
HashMap stores key-value pairs.
Keys are unique.
Values can be duplicated.
HashMap generally permits one null key and multiple null values.
[break:3s]
## question 106.
Why are equals and hashCode important for HashMap and HashSet?
Think carefully.
[break:10s]
Answer.
Hash-based collections use hashCode to help determine where an object belongs and equals to determine logical equality.
Equal objects must produce the same hash code.
If you override equals, you should follow the hashCode contract.
[break:3s]
## question 107.
What is exception handling?
Think now.
[break:6s]
Answer.
Exception handling allows a program to deal with exceptional situations without abruptly terminating normal program flow.
Java provides try, catch, finally, throw and throws.
[break:3s]
## question 108.
What is the difference between checked and unchecked exceptions?
Think now.
[break:8s]
Answer.
Checked exceptions are checked by the compiler and generally must be handled or declared.
Unchecked exceptions are RuntimeException subclasses and are not required to be caught or declared by the compiler.
[break:3s]
## question 109.
What is the difference between final, finally and finalize?
Think carefully.
[break:10s]
Answer.
final is a Java keyword.
It can be used for constants, methods that should not be overridden and classes that should not be extended.
finally is a block used for cleanup logic.
finalize was an old garbage-collection-related mechanism and has been deprecated.
It should not be relied upon in modern Java.
[break:3s]
## question 110.
What is a lambda expression?
Think now.
[break:7s]
Answer.
A lambda expression provides a concise way to represent behavior, especially for functional interfaces.
For example:
x -> x * 2
means take x and return x multiplied by two.
[break:3s]
## question 111.
What is a Java Stream?
Think now.
[break:7s]
Answer.
A Stream provides a declarative way to process data.
Common operations include filter, map, sorted, distinct and collect.
[break:3s]
## question 112.
What is the difference between map and filter?
Think now.
[break:8s]
Answer.
filter decides which elements remain.
map transforms each element into another value.
For example, filter can keep employees whose salary is greater than fifty thousand.
map can convert employees into employee names.
[break:3s]
That completes the Java section.
Now we move into manual testing and Selenium.
[break:4s]
PART 4.
MANUAL TESTING AND SELENIUM.
[break:3s]
## question 113.
What is SDLC?
Think now.
[break:6s]
Answer.
SDLC means Software Development Life Cycle.
It describes the overall process of developing software.
Typical stages include requirements, design, development, testing, deployment and maintenance.
[break:3s]
## question 114.
What is STLC?
Think now.
[break:6s]
Answer.
STLC means Software Testing Life Cycle.
It focuses specifically on testing activities.
Typical activities include requirement analysis, test planning, test-case design, environment setup, test execution, defect reporting and test closure.
[break:3s]
## question 115.
What is the difference between a test scenario and a test case?
Think now.
[break:7s]
Answer.
A test scenario is a high-level condition or functionality that needs to be tested.
A test case provides detailed steps, test data, expected results and execution information.
[break:3s]
## question 116.
What is severity versus priority?
Think carefully.
[break:9s]
Answer.
Severity describes the impact of a defect on the system.
Priority describes how urgently the defect should be addressed.
A high-severity defect does not automatically mean the highest business priority in every situation.
[break:3s]
## question 117.
What is regression testing?
Think now.
[break:6s]
Answer.
Regression testing verifies that recent changes have not broken existing functionality.
[break:3s]
## question 118.
What is retesting?
Think now.
[break:6s]
Answer.
Retesting verifies that a particular defect has been fixed.
Regression testing is broader.
Retesting focuses on the specific failed functionality.
[break:3s]
## question 119.
What is smoke testing?
Think now.
[break:6s]
Answer.
Smoke testing is a relatively broad but shallow check to determine whether a build is stable enough for detailed testing.
[break:3s]
## question 120.
What is sanity testing?
Think now.
[break:6s]
Answer.
Sanity testing is a focused check of specific functionality after changes or fixes.
Terminology can vary between organizations, so focus on the purpose.
[break:3s]
## question 121.
What is boundary value analysis?
Think now.
[break:7s]
Answer.
Boundary value analysis focuses on values at and around input boundaries.
For example, if age must be between 18 and 60, useful values include 17, 18, 19, 59, 60 and 61.
[break:3s]
## question 122.
What is equivalence partitioning?
Think now.
[break:7s]
Answer.
Equivalence partitioning divides input values into groups expected to behave similarly.
Instead of testing every value, you select representative values from each group.
[break:3s]
## question 123.
Imagine a login page.
What would you test?
Think carefully.
[break:12s]
Answer.
Valid username and password.
Invalid username.
Invalid password.
Both invalid.
Empty username.
Empty password.
Both empty.
Password masking.
Error messages.
Account lockout if applicable.
Forgot password.
Remember me if available.
Session behavior.
Successful logout.
Security-related behavior where appropriate.
And browser compatibility.
[break:3s]
## question 124.
What is Selenium WebDriver?
Think now.
[break:6s]
Answer.
Selenium WebDriver is an API used to automate browser interactions.
It allows automation code to control browsers and interact with web elements.
[break:3s]
## question 125.
What are Selenium locators?
Think now.
[break:6s]
Answer.
Locators identify elements on a web page.
Common strategies include ID, name, class name, tag name, link text, partial link text, CSS selector and XPath.
[break:3s]
## question 126.
Which locator would you prefer when a stable unique ID is available?
Think now.
[break:6s]
Answer.
A stable unique ID is usually a good choice because it is simple and direct.
But stability is more important than simply choosing ID.
A stable CSS selector can be better than an unstable ID.
[break:3s]
## question 127.
What is XPath?
Think now.
[break:6s]
Answer.
XPath is an expression language used to locate elements in an HTML or XML document structure.
It can locate elements using attributes, text, hierarchy and relationships.
[break:3s]
## question 128.
What is the difference between absolute and relative XPath?
Think now.
[break:8s]
Answer.
An absolute XPath starts from the root of the document hierarchy.
It can be fragile.
A relative XPath identifies an element using useful attributes or relationships.
Relative XPath is generally easier to maintain.
[break:3s]
## question 129.
Why should you avoid Thread.sleep everywhere?
Think carefully.
[break:8s]
Answer.
Thread.sleep waits for a fixed amount of time whether the application is ready or not.
It can make tests slow.
It can also fail if the application takes longer than the sleep duration.
Explicit waits are generally better for synchronization.
[break:3s]
## question 130.
What is an implicit wait?
Think now.
[break:6s]
Answer.
An implicit wait tells WebDriver to wait for a specified amount of time when locating elements before throwing a no-such-element exception.
[break:3s]
## question 131.
What is an explicit wait?
Think now.
[break:7s]
Answer.
An explicit wait waits for a specific condition.
For example, waiting until an element is visible or clickable.
It is more targeted than a fixed sleep.
[break:3s]
## question 132.
What is FluentWait?
Think now.
[break:7s]
Answer.
FluentWait provides configurable polling behavior and allows you to specify conditions and exceptions that should be ignored while waiting.
It gives more control over synchronization.
[break:3s]
## question 133.
Why do Selenium tests become flaky?
Think carefully.
[break:10s]
Answer.
Common causes include timing issues, unstable locators, asynchronous application behavior, stale elements, test-data problems, environment instability and incorrect synchronization.
[break:3s]
## question 134.
A button is visible but Selenium cannot click it.
What would you investigate?
Think now.
[break:12s]
Answer.
Check whether another element is covering it.
Check whether it is enabled.
Check whether the page is still loading.
Check whether the element became stale.
Check whether you are inside the correct frame.
Check whether the locator identifies the intended element.
Check whether an overlay or popup is present.
And check whether an explicit wait for clickability is needed.
[break:3s]
## question 135.
How do you handle an iframe?
Think now.
[break:7s]
Answer.
Switch into the frame.
For example:
driver.switchTo().frame(frameElement);
Then interact with elements inside it.
Afterward:
driver.switchTo().defaultContent();
[break:3s]
## question 136.
How do you handle an alert?
Think now.
[break:6s]
Answer.
Use:
driver.switchTo().alert();
Then you can accept, dismiss, retrieve text or enter text depending on the alert.
[break:3s]
## question 137.
How do you switch between browser windows?
Think now.
[break:7s]
Answer.
Use window handles.
You can obtain them using getWindowHandles.
Then switch to the required window handle.
[break:3s]
## question 138.
What is Page Object Model?
Think now.
[break:7s]
Answer.
Page Object Model is a design pattern where page-specific elements and actions are organized into page classes.
It separates test logic from page interaction logic.
This improves maintainability and reuse.
[break:3s]
## question 139.
What is PageFactory?
Think now.
[break:6s]
Answer.
PageFactory is a Selenium-supported approach historically used to initialize elements represented with annotations such as FindBy.
It can simplify page-object code.
But PageFactory and Page Object Model are not the same thing.
[break:3s]
## question 140.
What is TestNG?
Think now.
[break:6s]
Answer.
TestNG is a Java testing framework.
It supports annotations, configuration, grouping, dependencies, parameterization, data providers and test execution features.
[break:3s]
## question 141.
Name some common TestNG annotations.
Think now.
[break:7s]
Answer.
Test.
BeforeMethod.
AfterMethod.
BeforeClass.
AfterClass.
BeforeSuite.
AfterSuite.
BeforeTest.
AfterTest.
[break:3s]
## question 142.
What is Maven?
Think now.
[break:6s]
Answer.
Maven is a build and dependency-management tool.
In Java automation projects it can manage dependencies, compile code, run tests through plugins and package projects.
The main configuration file is pom.xml.
[break:3s]
## question 143.
Your Selenium test passes locally but fails on another machine.
What would you investigate?
Think carefully.
[break:12s]
Answer.
Browser version.
Driver version.
Operating system.
Java version.
Dependency versions.
Environment variables.
Application URL.
Test data.
Timing.
Network conditions.
Browser configuration.
And whether the test has hidden dependencies on your local machine.
[break:3s]
## question 144.
An automation test fails three times out of ten.
What would you do?
Think carefully.
[break:12s]
Answer.
First determine whether the failure is deterministic or intermittent.
Inspect logs and screenshots.
Identify the exact failure point.
Check synchronization.
Check test data.
Check locator stability.
Check environment conditions.
Check whether tests interfere with each other.
Then fix the underlying cause rather than simply adding a long sleep.
[break:3s]
That completes the testing and Selenium section.
Now we move into DSA.
[break:4s]
PART 5.
DSA.
This section is shorter.
The purpose is to train basic problem-solving ability.
[break:3s]
## question 145.
What is the time complexity of accessing an element by index in an ArrayList?
Think now.
[break:6s]
Answer.
Typically O of one.
Constant time.
[break:3s]
## question 146.
What is the average time complexity of HashMap lookup?
Think now.
[break:7s]
Answer.
Average-case lookup is generally O of one.
Worst-case behavior can be worse depending on collisions and implementation details.
[break:3s]
## question 147.
What is the time complexity of binary search?
Think now.
[break:6s]
Answer.
O of log N.
The data must satisfy the requirements of binary search, such as being sorted.
[break:3s]
## question 148.
You have the array:
2, 7, 11, 15.
The target is 9.
Can you find two numbers that add up to 9?
Think now.
[break:10s]
Answer.
Yes.
2 plus 7 equals 9.
This is the classic Two Sum problem.
[break:3s]
## question 149.
How could you solve Two Sum efficiently?
Think now.
[break:12s]
Answer.
Use a HashMap.
For each number, calculate the complement.
The complement is target minus the current number.
Check whether that complement already exists in the map.
If it does, you found the pair.
Otherwise, store the current number.
This can achieve average O of N time.
[break:3s]
## question 150.
What is the two-pointer technique?
Think now.
[break:7s]
Answer.
Two pointers means maintaining two positions in a data structure and moving them according to the problem's conditions.
It is commonly used with sorted arrays or strings.
[break:3s]
## question 151.
When is sliding window useful?
Think now.
[break:7s]
Answer.
Sliding window is useful for problems involving contiguous subarrays or substrings.
Instead of repeatedly calculating the entire range, you maintain a moving window and update it as it moves.
[break:3s]
## question 152.
What is the difference between time complexity and space complexity?
Think now.
[break:7s]
Answer.
Time complexity describes how running time grows with input size.
Space complexity describes how additional memory requirements grow with input size.
[break:3s]
## question 153.
What is the time complexity of a single loop through an array of N elements?
Think now.
[break:5s]
Answer.
O of N.
Each element is processed once.
[break:3s]
## question 154.
What is the time complexity of two nested loops, each running N times?
Think now.
[break:6s]
Answer.
O of N squared.
[break:3s]
## question 155.
What is recursion?
Think now.
[break:6s]
Answer.
Recursion is when a function calls itself to solve a smaller version of the same problem.
A recursive solution needs a base condition.
Without a proper base condition, the recursion can continue until a stack overflow occurs.
[break:3s]
FINAL MOCK INTERVIEW ROUND.
Now we are going to combine everything.
These ## questions are designed to feel more like an actual interview.
Do not worry if some of them are difficult.
Try to reason through them.
[break:4s]
## question 156.
An interviewer asks:
Explain the difference between WHERE, GROUP BY, HAVING and ORDER BY.
Think carefully.
[break:12s]
Answer.
WHERE filters rows.
GROUP BY creates groups.
HAVING filters groups.
ORDER BY sorts the result.
A useful mental sequence is:
Filter rows.
Create groups.
Filter groups.
Sort the result.
[break:3s]
## question 157.
An interviewer asks:
Why did your LEFT JOIN suddenly behave like an INNER JOIN?
Think carefully.
[break:15s]
Answer.
A common reason is placing a condition on the right-side table inside the WHERE clause.
For example:
SELECT *
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id
WHERE d.location = 'Chennai';
The WHERE condition removes rows where the department is NULL.
That can effectively eliminate unmatched employees.
Depending on the requirement, the condition may belong in the JOIN condition instead.
For example:
ON e.department_id = d.department_id
AND d.location = 'Chennai';
This is a very important SQL interview concept.
[break:3s]
## question 158.
Your SQL query returns duplicate employees after a join.
What could be happening?
Think carefully.
[break:12s]
Answer.
The relationship may be one-to-many.
One employee may match multiple rows in the other table.
The join condition may be incomplete.
There may be duplicate source data.
Or the business requirement may actually require multiple matching rows.
Do not immediately solve the problem using DISTINCT.
First understand why the duplicates exist.
[break:3s]
## question 159.
An ETL target has the correct number of rows, but several values are wrong.
Is row-count validation enough?
Think now.
[break:8s]
Answer.
No.
Row count verifies quantity.
It does not verify correctness.
You also need value-level validation, transformation validation, NULL checks, duplicate checks, business-rule validation and reconciliation.
[break:3s]
## question 160.
An interviewer asks:
How would you test an ETL mapping?
Think carefully.
[break:15s]
Answer.
First understand the source-to-target mapping.
Identify source columns and target columns.
Verify data types.
Verify transformations.
Verify joins.
Verify filters.
Verify default values.
Verify NULL handling.
Verify duplicate handling.
Compare row counts.
Compare key values.
Validate aggregates.
Check rejected records.
And verify incremental-load behavior where applicable.
[break:3s]
## question 161.
Your Selenium test uses a five-second sleep before clicking every button.
The interviewer asks why.
What would you say?
Think now.
[break:10s]
Answer.
I would explain that fixed sleeps can make automation slower and less reliable.
A better approach is to synchronize with the actual application state using explicit waits and appropriate expected conditions.
[break:3s]
## question 162.
Your Selenium test says element not found.
What are the first things you would check?
Think carefully.
[break:12s]
Answer.
Check the locator.
Check whether the page is loaded.
Check whether the element is inside an iframe.
Check whether it is dynamically created.
Check whether the page has changed.
Check whether the element is in another window.
Check timing and synchronization.
And inspect the DOM.
[break:3s]
## question 163.
An interviewer asks:
What is the difference between ArrayList and LinkedList?
Think now.
[break:8s]
Answer.
ArrayList is backed by a dynamically resizable array and provides efficient random access by index.
LinkedList is a linked data structure.
The performance difference depends on the operation and access pattern.
Do not simply say that LinkedList is always faster for insertion.
The actual location and operation matter.
[break:3s]
## question 164.
An interviewer asks:
Why do you want to improve your SQL and ETL skills?
Think now.
[break:10s]
Answer.
A strong answer could be:
I want to strengthen my data-oriented technical skills because SQL and ETL are important for many enterprise applications and data workflows.
I am currently focusing on becoming strong in querying, data validation, transformation logic and problem solving.
I want to be able to work confidently with real data rather than only knowing SQL syntax.
[break:3s]
## question 165.
Final interview ## question.
Tell me about your technical profile without exaggerating your experience.
Think about your answer.
[break:15s]
Answer.
A good structure would be:
My technical background is around software development and testing, with a current focus on SQL and ETL.
I have worked with Java, Selenium, TestNG, Maven and software-testing concepts.
I am also developing my Python and machine-learning skills.
At the moment, I am particularly strengthening SQL, data validation, ETL concepts and problem solving because I want to move into roles where I can apply these skills more deeply.
I also try to be clear about the difference between technologies I have worked with professionally and technologies I am currently learning.
That is a much stronger approach than claiming expert-level experience in everything.
[break:5s]
FINAL RECAP.
You have completed today's gym interview session.
Take a moment.
[break:5s]
The most important area is SQL.
You should become comfortable with:
SELECT.
WHERE.
GROUP BY.
HAVING.
ORDER BY.
DISTINCT.
NULL.
Constraints.
Primary keys.
Foreign keys.
Joins.
Subqueries.
EXISTS.
IN.
NOT IN.
Aggregate functions.
CASE.
COALESCE.
CTEs.
Window functions.
Indexes.
Views.
Transactions.
And practical SQL problems.
[break:4s]
For SQL interview practice, focus especially on:
Second-highest salary.
Nth-highest salary.
Duplicate records.
Nth row.
Top N records.
Top N per department.
Employees without departments.
Employees earning more than managers.
And understanding why joins create unexpected rows.
[break:4s]
For ETL, remember:
Source.
Extract.
Transform.
Validate.
Load.
Then validate again.
Do not rely only on row counts.
Think about:
Duplicates.
NULLs.
Data quality.
Reconciliation.
Transformation rules.
Incremental loads.
Full loads.
SCD Type 1.
SCD Type 2.
Facts.
Dimensions.
And source-to-target validation.
[break:4s]
For Java, focus on:
OOP.
Encapsulation.
Inheritance.
Polymorphism.
Abstraction.
Interfaces.
Abstract classes.
Strings.
Collections.
ArrayList.
LinkedList.
HashSet.
HashMap.
Exceptions.
equals.
hashCode.
Streams.
And lambdas.
[break:4s]
For testing, focus on:
SDLC.
STLC.
Test scenarios.
Test cases.
Severity.
Priority.
Regression.
Retesting.
Smoke.
Sanity.
Boundary value analysis.
Equivalence partitioning.
And real testing scenarios.
[break:4s]
For Selenium, focus on:
Locators.
XPath.
CSS selectors.
Explicit waits.
Implicit waits.
Fluent waits.
Frames.
Windows.
Alerts.
Actions.
WebDriver.
WebElement.
Page Object Model.
PageFactory.
TestNG.
Maven.
And framework design.
[break:4s]
For DSA, keep practicing:
Arrays.
Strings.
HashMap.
HashSet.
Two pointers.
Sliding window.
Searching.
Sorting.
Recursion.
Time complexity.
Space complexity.
[break:4s]
And remember one final thing.
You do not need to know everything before you start interviewing.
You need to continuously improve your ability to understand a ## question, think clearly, and explain your reasoning.
If you don't know an answer, do not panic.
Think about the problem.
Break it into smaller pieces.
Explain what you know.
And be honest about what you do not know.
[break:4s]
Your immediate technical priority is SQL and ETL.
Your supporting skills are Java, testing, Selenium and TestNG.
Your secondary long-term skills are Python, machine learning and DSA.
Keep building them step by step.
[break:5s]
Today's gym session is complete.
Keep training.
Keep solving.
Keep improving.
And most importantly, keep turning the concepts you learn into actual hands-on practice.
End of today's 90-minute gym interview session.

