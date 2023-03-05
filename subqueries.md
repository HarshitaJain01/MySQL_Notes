## Execute a failing query (i.e. one which gives an error) to retrieve all employees records whose salary is lower than the average salary.
### select * from employees where salary < AVG(salary);

## Execute a working query using a sub-select to retrieve all employees records whose salary is lower than the average salary.
### select EMP_ID, F_NAME, L_NAME, SALARY from employees where SALARY < (select AVG(SALARY) from employees);

## Execute a failing query (i.e. one which gives an error) to retrieve all employees records with EMP_ID, SALARY and maximum salary as MAX_SALARY in every row.
### select EMP_ID, SALARY, MAX(SALARY) AS MAX_SALARY from employees;

## Execute a Column Expression that retrieves all employees records with EMP_ID, SALARY and maximum salary as MAX_SALARY in every row.
### select EMP_ID, SALARY, ( select MAX(SALARY) from employees ) AS MAX_SALARY from employees;

## Execute a Table Expression for the EMPLOYEES table that excludes columns with sensitive employee data (i.e. does not include columns: SSN, B_DATE, SEX, ADDRESS, SALARY).
### select * from ( select EMP_ID, F_NAME, L_NAME, DEP_ID from employees) AS EMP4ALL;

## How does an Implicit version of CROSS JOIN (also known as Cartesian Join) statement syntax look?
### SELECT column_name(s) FROM table1, table2;

## How does an Implicit version of INNER JOIN statement syntax look?
### SELECT column_name(s) FROM table1, table2 WHERE table1.column_name = table2.column_name;

## Retrieve only the EMPLOYEES records that correspond to jobs in the JOBS table.
### select * from employees where JOB_ID IN (select JOB_IDENT from jobs);

## Retrieve only the list of employees whose JOB_TITLE is Jr. Designer.
### select * from employees where JOB_ID IN (select JOB_IDENT from jobs where JOB_TITLE= 'Jr. Designer');

## Retrieve JOB information and who earn more than $70,000.
### select JOB_TITLE, MIN_SALARY,MAX_SALARY,JOB_IDENT from jobs where JOB_IDENT IN (select JOB_ID from employees where SALARY > 70000 );

## Retrieve JOB information and whose birth year is after 1976.
### select JOB_TITLE, MIN_SALARY,MAX_SALARY,JOB_IDENT from jobs where JOB_IDENT IN (select JOB_ID from employees where YEAR(B_DATE)>1976 );

## Retrieve JOB information for female employees whose birth year is after 1976.
### select JOB_TITLE, MIN_SALARY,MAX_SALARY,JOB_IDENT from jobs where JOB_IDENT IN (select JOB_ID from employees where YEAR(B_DATE)>1976 and SEX='F' );


