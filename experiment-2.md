# Experiment No: 2 - Implementation of DML Commands in SQL

## Objective
- To understand the different issues involved in the design and implementation of a database system
- To understand and use data manipulation language to query, update, and manage a database

## Data Manipulation Language (DML) Commands

### 1. INSERT INTO
Used to add records into a relation.

**a) Inserting a single record with specified fields:**
```sql
INSERT INTO <table_name> (field_1, field_2, ..., field_n) 
VALUES (data_1, data_2, ..., data_n);
```
**Example:** `INSERT INTO student(sno, sname, class, address) VALUES (1, 'Ravi', 'M.Tech', 'Palakol');`

**b) Inserting a single record for all fields:**
```sql
INSERT INTO <table_name> VALUES (data_1, data_2, ..., data_n);
```
**Example:** `INSERT INTO student VALUES (1, 'Ravi', 'M.Tech', 'Palakol');`

**c) Inserting records from another relation:**
```sql
INSERT INTO table_name_1 
SELECT field_1, field_2, ..., field_n 
FROM table_name_2 
WHERE condition;
```
**Example:** `INSERT INTO std SELECT sno, sname FROM student WHERE name = 'Ramu';`

**d) Inserting multiple records (interactive):**
```sql
INSERT INTO table_name (field_1, field_2, ..., field_n)
VALUES (&data_1, '&data_2', ..., '&data_n');
```

### 2. UPDATE
Used to modify existing records in a table.

```sql
UPDATE table_name 
SET field_name1 = data1, field_name2 = data2, ... 
WHERE condition;
```
**Example:** `UPDATE student SET sname = 'kumar' WHERE sno = 1;`

### 3. DELETE
Used to remove records from a table.

**a) Delete all records:**
```sql
DELETE FROM table_name;
```
**Example:** `DELETE FROM std;`

**b) Delete specific records:**
```sql
DELETE FROM table_name WHERE condition;
```
**Example:** `DELETE FROM student WHERE sno = 2;`

### 4. TRUNCATE
Removes all data from a table but preserves the structure.

```sql
TRUNCATE TABLE table_name;
```
**Example:** `TRUNCATE TABLE student;`

**Differences between TRUNCATE and DELETE:**
- TRUNCATE removes data permanently (no rollback) while DELETE allows rollback
- DELETE can use WHERE conditions while TRUNCATE cannot
- TRUNCATE is a DDL command while DELETE is a DML command

### 5. SELECT
Used to retrieve data from one or more tables.

**a) Retrieve all fields from a table:**
```sql
SELECT * FROM table_name;
```
**Example:** `SELECT * FROM dept;`

**b) Retrieve specific fields:**
```sql
SELECT field_1, field_2, ... FROM table_name;
```
**Example:** `SELECT deptno, dname FROM dept;`

**c) Retrieve with conditions:**
```sql
SELECT fields FROM table_name WHERE condition;
```
**Example:** `SELECT * FROM dept WHERE deptno <= 20;`

## Practice Assignment
Create a table EMPLOYEE with schema: (Emp_no, E_name, E_address, E_ph_no, Dept_no, Dept_name, Job_id, Salary)

Write SQL queries for:
1. Insert at least 5 rows in the table
2. Display all information from the EMPLOYEE table
3. Display records of employees who work in department D10
4. Update the city of Emp_no-12 with current city as Nagpur
5. Display details of Employee who works in department MECH
6. Delete the email_id of employee James
7. Display the complete record of employees working in SALES Department
