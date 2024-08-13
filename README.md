# Applying-filters-to-SQL-Queries
# Scenario 
You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.
Your task is to examine the organization’s data in their **employees** and **log_in_attempts** tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.
# Project Overview
My role involves enhancing the security of our system, which includes ensuring the safety of the system, investigating potential security threats, and updating employee computers as required. Below, I outline how I utilised SQL with filters to address various security tasks.

## Identify Failed Logins After Hours
I detected a potential security issue involving failed login attempts outside of regular business hours (post-18:00). The SQL query below illustrates how I filtered for these failed logins:

<img width="628" alt="Screenshot 2024-08-13 at 10 42 14" src="https://github.com/user-attachments/assets/f4b42b70-110b-4e09-bd05-1fca0fb3be68">

This query retrieves records from log_in_attempts where login attempts occurred after 18:00 and were unsuccessful.

## Filter Login Attempts on Specific Dates
A suspicious event was reported on the 9th of May 2022. To investigate, I needed to filer login activity from 09/05 22 and the preceding day. Here is the SQL query I used:


This query extracts all login attempts for the dates in question

## Identify Login Attempts from Non-Mexican Locations
Upon reviewing login attempt data, I found potential issues with logins originating from outside Mexico. The following query was used to filter these attempts:


This retrieves login attempts from countries other than Mexico, where 'MEX' and 'MEXICO' are used to denote Mexico.

## Retrieve Employees in Marketing
To update computers for employees in the Marketing department located in the East building, I used the following query:


This query selects employees in the Marketing department within the East building.

## Retrieve Employees in Finance or Sales
To apply a different security update for employees in the Finance and Sales departments, the following SQL query was employed:


This retrieves employees from either the Finance or Sales departments.

## Identify Employees Not in IT
Finally, for a security update for employees outside the Information Technology department, I used this query:


This query selects all employees not working in the IT department.

# Summary
I applied various SQL filters to extract specific information from the **'log_in_attempts'** and **'employees tables'**. By using operators such as AND, OR, and NOT, along with wildcard patterns, I was able to obtain the necessary data for each task.
