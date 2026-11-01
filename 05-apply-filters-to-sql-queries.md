# Apply Filters to SQL Queries

## Project description

As a security professional at a large organization, I came across a few potential security issues tied to employee login attempts and work machines. As such, my main task in this project was to use SQL filters to pull the relevant records from our `log_in_attempts` and `employees` tables so I could investigate those issues.

## Retrieve after-hours failed login attempts

One of these issues was a potential security incident that happened after business hours, so I needed to find every failed login attempt recorded after 18:00.

I used SQL filters to display all columns in the `log_in_attempts` table and filter for records where the `login_time` column had a time value greater than (later than) 18:00 and where the `success` column had a value of 0, meaning FALSE (using the AND operator).

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```

## Retrieve login attempts on specific dates

Next, I looked into a suspicious event on 2022-05-09, which meant reviewing every login attempt from that day and the day before.

I used SQL filters to display all columns in the `log_in_attempts` table and filter for records where the `login_date` column had either a date value of 2022-05-09 or a date value of 2022-05-08 (using the OR operator).

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

## Retrieve login attempts outside of Mexico

The team also flagged suspicious login activity that it had confirmed did not come from Mexico, so I needed to find every login attempt made outside of Mexico.

I used SQL filters to display all columns in the `log_in_attempts` table and filter for records where the `country` column did not have a value starting with 'MEX' (using the NOT operator with LIKE 'MEX%'). The `country` column uses both 'MEX' and 'MEXICO' to refer to Mexico, and the % wildcard covers both, since it stands in for any characters after 'MEX', or none at all.

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

## Retrieve employees in Marketing

My team also planned security updates for certain machines in the Marketing department, so I needed to find every Marketing employee with an office in the East building.

I used SQL filters to display all columns in the `employees` table and filter for records where the `department` column had a value of 'Marketing' and the `office` column had a value starting with 'East' (using the AND operator with LIKE 'East%'), since all offices in the East building start with 'East' (for example, East-170).

```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```

## Retrieve employees in Finance or Sales

A different security update was planned for machines in the Finance and Sales departments, so I had to find every employee in either one.

I used SQL filters to display all columns in the `employees` table and filter for records where the `department` column had either a value of 'Finance' or a value of 'Sales' (using the OR operator).

```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```

## Retrieve all employees not in IT

Finally, one more update had to go out to every employee machine outside the Information Technology department, since IT had already received it. Thus, I needed to find all employees not in IT.

I used SQL filters to display all columns in the `employees` table and filter for records where the `department` column did not have a value of 'Information Technology' (using the NOT operator).

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

## Summary

To address the potential security issues that came up, I used SQL filters on the `log_in_attempts` table to retrieve details on after-hours failed login attempts, login attempts on specific dates, and login attempts outside of Mexico. I then used SQL filters on the `employees` table to retrieve details on Marketing employees in the East building, employees in Finance or Sales, and all employees not in IT so our team could perform various security updates on their machines. All of these actions helped us investigate potential security issues and keep the system secure.
