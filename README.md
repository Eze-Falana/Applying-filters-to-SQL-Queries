# Applying-filters-to-SQL-Queries
# Scenario 
You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.
Your task is to examine the organization’s data in their **employees** and **log_in_attempts** tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.
# Project Overview
My role involves enhancing the security of our system, which includes ensuring the safety of the system, investigating potential security threats, and updating employee computers as required. Below, I outline how I utilised SQL with filters to address various security tasks.

## Identify Failed Logins After Hours
I detected a potential security issue involving failed login attempts outside of regular business hours (post-18:00). The SQL query below illustrates how I filtered for these failed logins:

<img width="628" alt="Screenshot 2024-08-13 at 10 42 14" src="https://github.com/user-attachments/assets/f4b42b70-110b-4e09-bd05-1fca0fb3be68">

The initial part of the screenshot shows the SQL query, while the latter part displays a sample of the resulting data. This query specifically targets failed login attempts that took place after 18:00. To achieve this, I began by retrieving all entries from the **'log_in_attempts'** table. I then applied a **'WHERE'** clause combined with an **'AND'** operator to narrow down the results to only those login attempts that were unsuccessful and occurred post-18:00. The query filters for records where **'login_time'** is greater than '18:00', and success is marked as **'FALSE'**, focusing on failed attempts.

## Filter Login Attempts on Specific Dates
A suspicious event was reported on the 9th of May 2022. To investigate, I needed to filer login activity from 09/05 22 and the preceding day. Here is the SQL query I used:

<img width="628" alt="Screenshot 2024-08-13 at 10 44 23" src="https://github.com/user-attachments/assets/bb945ef7-684b-4814-86e8-4c348d54180a">

The first section of the screenshot displays my SQL query, while the second section shows a snippet of the output. This query retrieves all login attempts made on either 9 May 2022 or 8 May 2022. I began by selecting all records from the **'log_in_attempts'** table. Next, I applied a **'WHERE'** clause with an **'OR'** operator to filter the results so that only login attempts from 9 May 2022 or 8 May 2022 are included. The first condition checks if **'login_date'** is '2022-05-09', and the second condition checks for '2022-05-08'.

## Identify Login Attempts from Non-Mexican Locations
Upon reviewing login attempt data, I found potential issues with logins originating from outside Mexico. The following query was used to filter these attempts:

<img width="623" alt="Screenshot 2024-08-13 at 10 48 46" src="https://github.com/user-attachments/assets/a3de9bd1-6001-48a2-b32c-5697e493d7d1">

The initial part of the screenshot illustrates my SQL query, while the latter part presents a sample of the results. This query identifies all login attempts made from locations outside Mexico. I began by extracting all entries from the **'log_in_attempts'** table. Then, I applied a **'WHERE'** clause using **'NOT'** to exclude entries from Mexico. To match the pattern, I used **'LIKE'** with **'MEX%'**, as the dataset denotes Mexico with both **'MEX'** and **'MEXICO'**. The **'%'** symbol is used with **'LIKE'** to represent any sequence of characters.

## Retrieve Employees in Marketing
To update computers for employees in the Marketing department located in the East building, I used the following query:

<img width="630" alt="Screenshot 2024-08-13 at 10 50 59" src="https://github.com/user-attachments/assets/c1b8d445-a75d-41ab-bb59-479eedd2ba41">

The first part of the screenshot shows the SQL query, and the second part displays a sample of the results. This query retrieves all employees working in the Marketing department located in the East building. I began by selecting all records from the **'employees'** table. Then, I applied a **'WHERE'** clause with an **'AND'** operator to filter for employees in the Marketing department and those based in the East building. I used **'LIKE'** with the pattern **'East%'** to match entries where the office column denotes the East building, including specific office numbers. The first condition, **'department' = 'Marketing'**, selects employees in the Marketing department, while the second condition, office **'LIKE' 'East%'**, targets those located in the East building.

## Retrieve Employees in Finance or Sales
To apply a different security update for employees in the Finance and Sales departments, the following SQL query was employed:

<img width="629" alt="Screenshot 2024-08-13 at 10 52 33" src="https://github.com/user-attachments/assets/c834f40e-a6bc-4bdc-a7b0-85b80f7ef506">

The initial part of the screenshot displays my SQL query, while the latter part shows a sample of the results. This query selects all employees from the Finance and Sales departments. I began by retrieving all records from the **'employees'** table. I then applied a **'WHERE'** clause with an **'OR'** operator to include employees from either the Finance or Sales departments. The use of **'OR'** allows for the inclusion of employees from both departments, whereas **'AND'** would restrict results to those in both. The first condition, **'department = 'Finance'**, targets employees in the Finance department, while the second condition, **'department = 'Sales'**, identifies those in the Sales department.

## Identify Employees Not in IT
Finally, for a security update for employees outside the Information Technology department, I used this query:

<img width="628" alt="Screenshot 2024-08-13 at 10 54 25" src="https://github.com/user-attachments/assets/b7e6a34c-5286-4480-b7be-87279f0e64c9">

The initial part of the screenshot presents my SQL query, while the latter part shows a sample of the results. This query retrieves details of all employees who are not in the Information Technology department. I began by selecting all entries from the **'employees'** table and then applied a **'WHERE'** clause with **'NOT'** to exclude those in the IT department.

# Summary
I applied various SQL filters to extract specific information from the **'log_in_attempts'** and **'employees tables'**. By using operators such as AND, OR, and NOT, along with wildcard patterns, I was able to obtain the necessary data for each task.
