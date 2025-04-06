# Experiment No: 1 - Implementation of DDL Commands in SQL

## Objective
- To understand the different issues involved in the design and implementation of a database system
- To understand and use Data Definition Language (DDL) to write queries for a database

## Oracle Tools Overview
- **SQL*PLUS**: Consists of Interactive SQL (for creating and manipulating data structures) and PL/SQL (for application development)
- **Oracle Forms**: Creates data entry screens with menu objects, handles data gathering and validation
- **Report Writer**: Prepares reports using data from Oracle structures like tables and views
- **Oracle Graphics**: Represents data in graphical form using Oracle data structures

## SQL (Structured Query Language)
- Designed for managing data in relational database management systems (RDBMS)
- Based on Relational Algebra, developed by IBM in the mid-1970s
- Incorporated by Oracle in 1979
- Used by IBM/DB2 and DS Database Systems
- Adopted as standard language for RDBMS by ANSI in 1989

## Important SQL Data Types
1. **CHAR(size)**: Fixed-length character strings (maximum 255 characters)
2. **VARCHAR(size)/VARCHAR2(size)**: Variable-length alphanumeric data (maximum 2000 characters)
3. **NUMBER(p,s)**: Stores fixed or floating-point numbers with precision p and scale s (up to 38 digits)
4. **DATE**: Represents date and time (standard format: DD-MM-YY, e.g., 17-SEP-2009)
5. **LONG**: Variable-length character strings up to 2GB, can store binary data in ASCII format
6. **RAW**: Stores binary data like images (maximum 255 bytes, LONG RAW can store up to 2GB)

## SQL Language Categories
1. **DATA DEFINITION LANGUAGE (DDL)**: Create and modify database structures
2. **DATA MANIPULATION LANGUAGE (DML)**: Manipulate data within database objects
3. **DATA RETRIEVAL LANGUAGE (DRL)**: Query and retrieve data
4. **TRANSACTION CONTROL LANGUAGE (TCL)**: Control database transactions
5. **DATA CONTROL LANGUAGE (DCL)**: Control access permissions

## DDL Commands in Detail

### 1. CREATE
Used to create new database objects such as tables

**CREATE TABLE Syntax:**
```sql
CREATE TABLE <table_name> (
    field_1 data_type(size),
    field_2 data_type(size),
    ...
);
```

**Example:**
```sql
CREATE TABLE Student (
    sno NUMBER(3),
    sname CHAR(10),
    class CHAR(5)
);
```

### 2. ALTER
Used to modify existing database objects

**ALTER TABLE...ADD: Add new columns**
```sql
ALTER TABLE table_name ADD (
    new_field_1 data_type(size),
    new_field_2 data_type(size),
    ...
);
```
**Example:** `ALTER TABLE std ADD (Address CHAR(10));`

**ALTER TABLE...MODIFY: Change column data type or size**
```sql
ALTER TABLE table_name MODIFY (
    field_1 new_data_type(size),
    field_2 new_data_type(size),
    ...
);
```
**Example:** `ALTER TABLE student MODIFY (sname VARCHAR(10), class VARCHAR(5));`

**ALTER TABLE...DROP: Remove columns**
```sql
ALTER TABLE table_name DROP COLUMN field_name;
```
**Example:** `ALTER TABLE student DROP COLUMN sname;`

**ALTER TABLE...RENAME: Change column names**
```sql
ALTER TABLE table_name RENAME COLUMN old_field_name TO new_field_name;
```
**Example:** `ALTER TABLE student RENAME COLUMN sname TO stu_name;`

### 3. DROP TABLE
Permanently deletes a table and all its data
```sql
DROP TABLE table_name;
```
**Example:** `DROP TABLE std;`

### 4. RENAME
Changes the name of an existing database object
```sql
RENAME TABLE old_table_name TO new_table_name;
```
**Example:** `RENAME TABLE std TO std1;`


