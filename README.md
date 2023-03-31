# sql-challenge
module 9 homework
used sql file from QuickDBD as a guide for table schemata 

creates six different tables to model, engineer, and analyze data from an employee database to get employee information during the 1980s and 1990s 

table 1 - titles - import csv file "titles" to create table.
Primary Key = "title_id" - VARCHAR - varying characters

table 2- employees - import csv file "employees" to create table
Primary Key = "emp_no" - INT - integer
Foreign Key = "emp_title_id" references "title_id" from table 1

table 3- departments - import csv file "departments" to create table
Primary Key = "dept_no" - VARCHAR - varying characters

table 4 - dept_manager - import csv file "dept_manager" to create table
Primary Key = composite of dept_no and emp_no
Foreign Key = emp_no References emp_no from table 2
Foreign Key = dept_no References dept_no from table 3

table 5- dept_emp - import csv file "dept_emp" to create table
Primary Key = composite of emp_no and dept_no columns
Foreign Key = emp_no References emp_no from table 2
Foreign Key = dept_no References dept_no from table 3

table 6 - Salaries - import csv file "salaries" to create table
Primary Key = emp_no - INT - Integer
Foreing Key = emp_no References emp_no form table 2

Create script two for Queries:
List the employee number, last name, first name, sex, and salary of each employee.
Created a left join to merge employee info from table 2 to salary info from table 6

List the first name, last name, and hire date for the employees who were hired in 1986.
Filtered data to find employees within the time frame by using "WHERE, BETWEEN, AND" because 1986 is a whole year.

List the manager of each department along with their department number, department name, employee number, last name, and first name.
created inner join to merge department info with dept_no column fromt table 4 then another inner join to merge employee with dept_manager info.

List the department number for each employee along with that employee’s employee number, last name, first name, and department name.
Created inner join to merge dept_emp info with employee info from table 2 then another inner join
to merge departments info with demp_no info from table 5

List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.
Used WHERE to find hercules AND and LIKE to find last name starting with B from table 2

List each employee in the Sales department, including their employee number, last name, and first name.
used inner join to merge dept_emp with employee info from table 2 then another inner join to merge departments with dept_no column from table 5

List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.
used inner join to merge dept_emp info with emp_no columb from table 2 the another inner join to merge departments info with dept_no column from table 5
then used WHERE to filter info according to sales and development departments only.

List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).
used last_name column from employees to list the frequence counts on "Last Name Count" column. 