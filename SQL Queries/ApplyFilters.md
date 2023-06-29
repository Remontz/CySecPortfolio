# Apply filters to SQL queries

## Project Description

Acting as security professional at a large organization; part of the job is to investigate security issues to help keep the system secure.  Recently I discovered some potential security issues that involve login attempts and employee machines.
    The task is to examine the organization's data in their `employee` and `log_in_attempts` tables.  I'll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

## Retrieve after hours failed login attempts

    [ SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = 0; ]
This will retrieve all(*) entries from the `log_in_attempts` table where the ``login_time`` is after 6PM(1800) and the login attempt was unsuccessful(0).

## Retrieve login attempts on specific dates

    [ SELECT * FROM log_in_attempts WHERE login_date = 2022-05-08 OR login_date = 2022-05-09; ]
This query will retrieve all login attempts made between 05/08 & 05/09

## Retrieve login attempts outside of Mexico

    [ SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%'; ]

## Retrieve employees in Marketing

    [ SELECT * FROM log_in_attempts WHERE department = 'Marketing'; ]

## Retrieve employees in Finance or Sales

    [ SELECT * FROM log_in_attempts WHERE department = 'Finance'; ]

## Retrieve all employees not in IT

    [ SELECT * FROM log_in_attempts WHERE NOT department = 'Information Technology'; ]

## Summary

    With the above queries I was able to tabulate specific data related to investigating the suspicious log_in activity at the organization.  With the data tabulated correlations can be drawn to which device no and/or departments were involved.
