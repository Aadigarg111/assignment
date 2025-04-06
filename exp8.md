# Experiment No: 8
## Title: Study & Implementation of different types of constraints

### Objective:
To practice and implement constraints

### Theory:

#### CONSTRAINTS:
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE statement) or after the table is created (using ALTER TABLE statement).

1. **NOT NULL:**
When a column is defined as NOT NULL, then that column becomes a mandatory column. It implies that a value must be entered into the column if the record is to be accepted for storage in the table.

**Syntax:**
```sql
CREATE TABLE Table_Name (column_name data_type (size) NOT NULL, );
```

**Example:**
```sql
CREATE TABLE student (sno NUMBER(3) NOT NULL, name CHAR(10));
```

2. **UNIQUE:**
The purpose of a unique key is to ensure that information in the column(s) is unique i.e. a value entered in column(s) defined in the unique constraint must not be repeated across the column(s). A table may have many unique keys.

**Syntax:**
```sql
CREATE TABLE Table_Name (column_name data_type(size) UNIQUE, ….);
```

**Example:**
```sql
CREATE TABLE student (sno NUMBER(3) UNIQUE, name CHAR(10));
```

3. **CHECK:**
Specifies a condition that each row in the table must satisfy. To satisfy the constraint, each row in the table must make the condition either TRUE or unknown (due to a null).

**Syntax:**
```sql
CREATE TABLE Table_Name (column_name data_type(size) CHECK(logical expression), ….);
```

**Example:**
```sql
CREATE TABLE student (sno NUMBER(3), name CHAR(10), class CHAR(5), CHECK(class IN('CSE','CAD','VLSI')));
```

4. **PRIMARY KEY:**
A field which is used to identify a record uniquely. A column or combination of columns can be created as primary key, which can be used as a reference from other tables. A table contains primary key is known as Master Table.
- It must uniquely identify each record in a table.
- It must contain unique values.
- It cannot be a null field.
- It cannot be multi port field.
- It should contain a minimum no. of fields necessary to be called unique.

**Syntax:**
```sql
CREATE TABLE Table_Name (column_name data_type(size) PRIMARY KEY, ….);
```

**Example:**
```sql
CREATE TABLE faculty (fcode NUMBER(3) PRIMARY KEY, fname CHAR(10));
```

5. **FOREIGN KEY:**
It is a table level constraint. We cannot add this at column level. To reference any primary key column from other table this constraint can be used. The table in which the foreign key is defined is called a detail table. The table that defines the primary key and is referenced by the foreign key is called the master table.

**Syntax:**
```sql
CREATE TABLE Table_Name (column_name data_type(size), FOREIGN KEY(column_name) REFERENCES table_name);
```

**Example:**
```sql
CREATE TABLE subject (scode NUMBER(3) PRIMARY KEY, subname CHAR(10), fcode NUMBER(3), FOREIGN KEY(fcode) REFERENCES faculty);
```

**Defining integrity constraints in the alter table command:**

**Syntax:**
```sql
ALTER TABLE Table_Name ADD PRIMARY KEY (column_name);
```

**Example:**
```sql
ALTER TABLE student ADD PRIMARY KEY (sno);
```

OR

**Syntax:**
```sql
ALTER TABLE table_name ADD CONSTRAINT constraint_name PRIMARY KEY(colname)
```

**Example:**
```sql
ALTER TABLE student ADD CONSTRAINT SN PRIMARY KEY(SNO)
```

**Dropping integrity constraints in the alter table command:**

**Syntax:**
```sql
ALTER TABLE Table_Name DROP constraint_name;
```

**Example:**
```sql
ALTER TABLE student DROP PRIMARY KEY;
```

OR

**Syntax:**
```sql
ALTER TABLE student DROP CONSTRAINT constraint_name;
```

**Example:**
```sql
ALTER TABLE student DROP CONSTRAINT SN;
```

6. **DEFAULT:**
The DEFAULT constraint is used to insert a default value into a column. The default value will be added to all new records, if no other value is specified.

**Syntax:**
```sql
CREATE TABLE Table_Name (col_name1, col_name2, col_name3 DEFAULT '<value>');
```

**Example:**
```sql
CREATE TABLE student (sno NUMBER(3) UNIQUE, name CHAR(10), address VARCHAR(20) DEFAULT 'Aurangabad');
```

### LAB PRACTICE ASSIGNMENT:
1. Create a table called EMP with the following structure:
   ```
   Name     Type
   EMPNO    NUMBER(6)
   ENAME    VARCHAR2(20)
   JOB      VARCHAR2(10)
   DEPTNO   NUMBER(3)
   SAL      NUMBER(7,2)
   ```
   Allow NULL for all columns except ename and job.
2. Add constraints to check, while entering the empno value (i.e) empno > 100.
3. Define the field DEPTNO as unique.
4. Create a primary key constraint for the table (EMPNO).
5. Write queries to implement and practice constraints.
