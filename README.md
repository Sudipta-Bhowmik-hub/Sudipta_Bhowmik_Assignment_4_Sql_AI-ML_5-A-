**Overview :
This repository contains a SQL assignment created as part of an internship submission.
The objective of this assignment is to demonstrate practical knowledge of SQL Time Functions and Window Functions using two relational tables.

**Tables Used :
1) Departments
dept_id (Primary Key)
dept_name

2) Employees
emp_id (Primary Key)
emp_name
dept_id (Foreign Key)
salary
joining_date

** SQL Concepts Implemented :
Time Functions (YEAR, MONTH, DATEDIFF)
ROW_NUMBER()
RANK()
DENSE_RANK()
PARTITION BY
FIRST_VALUE()
PERCENT_RANK()

## Sample Data (Employees Table)

| emp_id | emp_name | dept_id | salary | joining_date |
|--------|----------|---------|--------|--------------|
| 101    | Amit     | 1       | 40000  | 2022-01-15   |
| 102    | Riya     | 2       | 60000  | 2021-03-10   |
| 103    | Suman    | 2       | 55000  | 2023-06-20   |
| 104    | Rahul    | 3       | 70000  | 2020-09-05   |
| 105    | Neha     | 1       | 45000  | 2022-11-25   |


## Time Functions Output

| emp_name | joining_year | joining_month | days_in_company |
|----------|--------------|---------------|-----------------|
| Amit     | 2022         | 1             | 1080            |
| Riya     | 2021         | 3             | 1400            |
| Suman    | 2023         | 6             | 550             |
| Rahul    | 2020         | 9             | 1550            |
| Neha     | 2022         | 11            | 770             |

## ROW_NUMBER() Output

| emp_name | salary | row_num |
|----------|--------|---------|
| Rahul    | 70000  | 1       |
| Riya     | 60000  | 2       |
| Suman    | 55000  | 3       |
| Neha     | 45000  | 4       |
| Amit     | 40000  | 5       |


## RANK() Output

| emp_name | salary | rank |
|----------|--------|------|
| Rahul    | 70000  | 1    |
| Riya     | 60000  | 2    |
| Suman    | 55000  | 3    |
| Neha     | 45000  | 4    |
| Amit     | 40000  | 5    |


## DENSE_RANK() Output

| emp_name | salary | dense_rank |
|----------|--------|------------|
| Rahul    | 70000  | 1          |
| Riya     | 60000  | 2          |
| Suman    | 55000  | 3          |
| Neha     | 45000  | 4          |
| Amit     | 40000  | 5          |


## Department-wise Rank (PARTITION BY)

| emp_name | dept_id | salary | dept_rank |
|----------|---------|--------|-----------|
| Neha     | 1       | 45000  | 1         |
| Amit     | 1       | 40000  | 2         |
| Riya     | 2       | 60000  | 1         |
| Suman    | 2       | 55000  | 2         |
| Rahul    | 3       | 70000  | 1         |

## FIRST_VALUE() Output

| emp_name | dept_id | salary | highest_paid_employee |
|----------|---------|--------|-----------------------|
| Neha     | 1       | 45000  | Neha                  |
| Amit     | 1       | 40000  | Neha                  |
| Riya     | 2       | 60000  | Riya                  |
| Suman    | 2       | 55000  | Riya                  |
| Rahul    | 3       | 70000  | Rahul                 |


## PERCENT_RANK() Output

| emp_name | salary | percent_rank |
|----------|--------|--------------|
| Amit     | 40000  | 0.00         |
| Neha     | 45000  | 0.25         |
| Suman    | 55000  | 0.50         |
| Riya     | 60000  | 0.75         |
| Rahul    | 70000  | 1.00         |


**Tools Used : 
SQL (MySQL)
GitHub

** Explanations :
## Employees Table – Explanation
The Employees table stores employee details such as name, department, salary, and joining date.
The dept_id acts as a foreign key that connects each employee to a department.

Purpose:
Used to apply ranking and window functions .
Helps analyze salaries, experience, and department-wise performance .
Demonstrates real-world employee analytics .

## Time Functions – Explanation
Time functions are used to extract or calculate date-related information.
Functions Used:
YEAR(joining_date) → Extracts joining year
MONTH(joining_date) → Extracts joining month
DATEDIFF() → Calculates number of days an employee has worked

Use Case:
Used to measure employee experience and tenure in the organization.

## ROW_NUMBER() – Explanation
ROW_NUMBER() assigns a unique sequential number to each row based on a specified order.

Key Point:
Always generates unique numbers
Useful for pagination and unique ranking

Example Use:
Ranking employees based on salary.

## RANK() – Explanation
RANK() assigns a rank to rows but skips ranks when there are duplicate values.

Key Point:
Duplicate values get the same rank
Next rank is skipped

Example:
If two employees share the highest salary, both get rank 1, and the next rank will be 3.

## DENSE_RANK() – Explanation
DENSE_RANK() is similar to RANK() but does not skip ranks.

Key Point:
Duplicate values get the same rank
Ranking remains continuous

Example:
If two employees have the same salary, both get rank 1, and the next rank is 2.

## PARTITION BY – Explanation
PARTITION BY divides the result set into groups and applies window functions within each group.

Use Case:
Department-wise salary ranking
Comparing employees only within their own department

## FIRST_VALUE() – Explanation
FIRST_VALUE() returns the first value in a window based on a specified order.

Use Case:
Finding the highest-paid employee in each department
Identifying top performers

## PERCENT_RANK() – Explanation
PERCENT_RANK() calculates the relative rank of a row as a percentage.

Key Point:
Values range between 0 and 1
Helps understand an employee’s position relative to others

Example: An employee with percent_rank = 0.75 earns more than 75% of employees.

## Overall Learning Outcome
This assignment demonstrates:
Understanding of SQL analytical functions
Real-world employee data analysis
Ability to work with window functions and time-based calculations
Practical SQL skills required for internship and entry-level roles

** Conclusion : 
This assignment demonstrates effective use of SQL Window Functions and Time Functions for real-world employee data analysis.
It highlights ranking, partitioning, and analytical capabilities essential for database-driven applications.













