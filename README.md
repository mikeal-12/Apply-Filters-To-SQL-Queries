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
