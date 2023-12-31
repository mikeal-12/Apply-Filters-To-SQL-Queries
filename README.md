# Project description
My organization (fictional) is working to make their system more secure. It is my job to ensure the system
is safe, investigate all potential security issues, and update employee computers as needed.
The following steps provide examples of how I used SQL with filters to perform
security-related tasks.

## Retrieving after hours failed login attempts
There was a potential security incident that occurred after business hours <code>(after 18:00)</code>. All after
hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts
that occurred after business hours:

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/02610f24-874b-419b-930e-d1b08ed5fb20)


The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after <code>18:00</code>. First, I started by selecting all data from the <code>log_in_attempts table</code>. Then, I used a <code>WHERE</code> clause with an <code>AND</code> operator to filter my results to output only login attempts that occurred after <code>18:00</code> and were unsuccessful. The first condition is <code>login_time > '18:00'</code>, which filters for the login attempts that occurred after <code>18:00</code>. The second condition is <code>success = FALSE</code>, which filters for the failed login attempts. 

## Retrieving login attempts on specific dates
A suspicious event occurred on <code>2022-05-09</code>. Any login activity that happened on <code>2022-05-09</code>, or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/cde825ed-47e2-4832-a6e5-a0ac5b0b41f8)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on <code>2022-05-09</code> or <code>2022-05-08</code>. First, I started by selecting all data from the log_in_attempts table. Then, I used a <code>WHERE</code> clause with an <code>OR</code> operator to filter my results to output only login attempts that occurred on either <code>2022-05-09</code> or <code>2022-05-08</code>. The first condition is <code>login_date = '2022-05-09'</code>, which filters for logins on <code>2022-05-09</code>. The second condition is <code>login_date = '2022-05-08'</code>, which filters for logins on <code>2022-05-08</code>.

## Retrieving login attempts outside of Mexico
After investigating the organization’s data on login attempts, I believed there was an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/f4b9af7c-0e48-45d6-b9f0-00d8528a3665)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the <code>log_in_attempts</code> table. Then, I used a <code>WHERE</code> clause with <code>NOT</code> to filter for countries other than Mexico. I used <code>LIKE</code> with <code>MEX%</code> as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign <code>%</code> represents any number of unspecified characters when used with <code>LIKE</code>. 

## Retrieving employees in Marketing
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/df096c44-68e2-4964-90ee-edbad58a59ab)


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a <code>WHERE</code> clause with <code>AND</code> to filter for employees who work in the Marketing department and in the East building. I used <code>LIKE</code> with <code>East%</code> as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the <code>department = 'Marketing'</code> portion, which filters for employees in the Marketing department. The second condition is the office <code>LIKE 'East%'</code> portion, which filters for employees in the East building.

## Retrieving employees in Finance or Sales
The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/3d03af02-23d8-4673-b3fc-133e7fed3344)


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a <code>WHERE</code> clause with <code>OR</code> to filter for employees who are in the Finance and Sales departments. I used the <code>OR</code> operator instead of <code>AND</code> because I want all employees who are in either department. The first condition is <code>department = 'Finance'</code> , which filters for employees from the Finance department. The second condition is <code>department = 'Sales'</code>, which filters for employees from the Sales department.

## Retrieving all employees not in IT
My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

![image](https://github.com/mikeal-12/Apply-Filters-To-SQL-Queries/assets/72464155/f4729406-633d-4d68-a9f4-8efce43ad6de)


The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the <code>employees</code> table. Then, I used a <code>WHERE</code> clause with <code>NOT</code> to filter for employees not in this department.

## Summary
I applied filters to SQL queries to get specific information on <code>login attempts</code> and <code>employee</code> machines. I used two different tables, <code>log_in_attempts</code>, and <code>employees</code>. I used the <code>AND</code>, <code>OR</code>, and <code>NOT</code> operators to filter for the specific information needed for each task. I also used <code>LIKE</code> and the percentage sign <code>%</code> wildcard to filter for patterns.
