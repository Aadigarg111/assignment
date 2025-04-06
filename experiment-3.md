# Experiment No: 3 - Implementation of Different Types of Functions with Suitable Examples

## Objective
- To understand and implement various SQL functions for data manipulation and analysis
- To develop aggregate plan strategies to assist with summarization of data entries

## Types of SQL Functions

### 1. Number Functions
- **ABS(n)**: Returns absolute value
  - Example: `SELECT ABS(-15) FROM DUAL;` → 15
- **EXP(n)**: Returns e raised to the nth power
  - Example: `SELECT EXP(4) FROM DUAL;` → 54.598150033
- **POWER(m,n)**: Returns m raised to the nth power
  - Example: `SELECT POWER(4,2) FROM DUAL;` → 16
- **MOD(m,n)**: Returns remainder of m divided by n
  - Example: `SELECT MOD(10,3) FROM DUAL;` → 1
- **ROUND(m,n)**: Rounds m to n decimal places
  - Example: `SELECT ROUND(100.256,2) FROM DUAL;` → 100.26
- **TRUNC(m,n)**: Truncates m to n decimal places
  - Example: `SELECT TRUNC(100.256,2) FROM DUAL;` → 100.25
- **SQRT(n)**: Returns square root of n
  - Example: `SELECT SQRT(16) FROM DUAL;` → 4

### 2. Aggregate Functions
- **COUNT**: Returns the number of rows
  - Example: `SELECT COUNT(Sal) FROM emp;`
- **SUM**: Returns the sum of values in a column
  - Example: `SELECT SUM(Sal) FROM emp;`
- **AVG**: Returns the average value of a column
  - Example: `SELECT AVG(10, 15, 30) FROM DUAL;`
- **MAX**: Returns the maximum value in a column
  - Example: `SELECT MAX(Sal) FROM emp;`
  - Example with GROUP BY: `SELECT deptno, MAX(sal) FROM emp GROUP BY deptno;`
  - Example with HAVING: `SELECT deptno, MAX(sal) FROM emp GROUP BY deptno HAVING MAX(sal) < 3000;`
- **MIN**: Returns the minimum value in a column
  - Example: `SELECT MIN(Sal) FROM emp;`
  - Example with conditions: `SELECT deptno, MIN(sal) FROM emp GROUP BY deptno HAVING MIN(sal) > 1000;`

### 3. Character Functions
- **INITCAP(char)**: Converts first letter of each word to uppercase
  - Example: `SELECT INITCAP("hello") FROM DUAL;` → Hello
- **LOWER(char)**: Converts string to lowercase
  - Example: `SELECT LOWER('HELLO') FROM DUAL;` → hello
- **UPPER(char)**: Converts string to uppercase
  - Example: `SELECT UPPER('hello') FROM DUAL;` → HELLO
- **LTRIM(char,[set])**: Removes characters from left of string
  - Example: `SELECT LTRIM('cseit', 'cse') FROM DUAL;` → it
- **RTRIM(char,[set])**: Removes characters from right of string
  - Example: `SELECT RTRIM('cseit', 'it') FROM DUAL;` → cse
- **REPLACE(char,search)**: Replaces occurrences of a substring
  - Example: `SELECT REPLACE('jack and jue','j','bl') FROM DUAL;` → black and blue

### 4. Conversion Functions
- **TO_CHAR**: Converts number or date to string
  - Example: `SELECT TO_CHAR(65,'RN') FROM DUAL;` → LXV
- **TO_NUMBER**: Converts string to number
  - Example: `SELECT TO_NUMBER('1234.64') FROM DUAL;` → 1234.64
- **TO_DATE**: Converts string to date
  - Example: `SELECT TO_DATE('January 15, 1989, 11:00 A.M.') FROM DUAL;` → 15-JAN-89

### 5. String Functions
- **CONCAT**: Concatenates two strings
  - Example: `SELECT CONCAT('ORACLE','CORPORATION') FROM DUAL;` → ORACLECORPORATION
- **LPAD**: Left-pads a string to a specified length
  - Example: `SELECT LPAD('ORACLE',15,'*') FROM DUAL;` → *********ORACLE
- **RPAD**: Right-pads a string to a specified length
  - Example: `SELECT RPAD('ORACLE',15,'*') FROM DUAL;` → ORACLE*********
- **LENGTH**: Returns the number of characters in a string
  - Example: `SELECT LENGTH('DATABASE') FROM DUAL;` → 8
- **SUBSTR**: Returns a substring
  - Example: `SELECT SUBSTR('ABCDEFGHIJ',3,4) FROM DUAL;` → CDEF
- **INSTR**: Returns the position of a substring
  - Example: `SELECT INSTR('CORPORATE FLOOR','OR',3,2) FROM DUAL;` → 14

### 6. Date Functions
- **SYSDATE**: Returns current date and time
  - Example: `SELECT SYSDATE FROM DUAL;` → 29-DEC-08
- **NEXT_DAY**: Returns the date of the first weekday later than a date
  - Example: `SELECT NEXT_DAY(SYSDATE,'WED') FROM DUAL;` → 05-JAN-09
- **ADD_MONTHS**: Adds months to a date
  - Example: `SELECT ADD_MONTHS(SYSDATE,2) FROM DUAL;` → 28-FEB-09
- **LAST_DAY**: Returns the last day of the month
  - Example: `SELECT LAST_DAY(SYSDATE) FROM DUAL;` → 31-DEC-08
- **MONTHS_BETWEEN**: Returns months between two dates
  - Example: `SELECT MONTHS_BETWEEN(SYSDATE,HIREDATE) FROM EMP;` → 4
- **LEAST**: Returns the earliest date
  - Example: `SELECT LEAST('10-JAN-07','12-OCT-07') FROM DUAL;` → 10-JAN-07
- **GREATEST**: Returns the latest date
  - Example: `SELECT GREATEST('10-JAN-07','12-OCT-07') FROM DUAL;` → 10-JAN-07
- **TRUNC**: Truncates a date
  - Example: `SELECT TRUNC(SYSDATE,'DAY') FROM DUAL;` → 28-DEC-08
- **ROUND**: Rounds a date
  - Example: `SELECT ROUND(SYSDATE,'DAY') FROM DUAL;` → 28-DEC-08

## Practice Assignment
Create a table EMPLOYEE with schema: (Emp_no, E_name, E_address, E_ph_no, Dept_no, Dept_name, Job_id, Designation, Salary)

Write SQL statements for:
1. List the E_no, E_name, Salary of all employees working for MANAGER
2. Display all details of employees whose salary is more than the Salary of any IT PROF
3. List employees in ascending order of Designations who joined after 1981
4. List employees along with their Experience and Daily Salary
5. List employees who are either 'CLERK' or 'ANALYST'
6. List employees who joined on 1-MAY-81, 3-DEC-81, 17-DEC-81, 19-JAN-80
7. List employees working for Deptno 10 or 20
8. List Enames starting with 'S'
9. Display the name and first five characters of names starting with 'H'
10. List all employees except 'PRESIDENT' & 'MGR' in ascending order of Salaries
