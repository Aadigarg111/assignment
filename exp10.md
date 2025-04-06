# Experiment No: 10
## Title: Creating Database/ Table Space
- Managing Users: - Create User, Delete User
- Managing Passwords
- Managing roles: - Grant, Revoke

### Objective:
To understand the concept of administrative commands

### Theory:

#### DATABASE:
A DATABASE is collection of coherent data.

To create database we have:

**Syntax:**
```sql
CREATE DATABASE <database_name>
```

**Example:**
```sql
CREATE DATABASE my_db;
```

#### TABLESPACE:
The Oracle database consists of one or more logical storage units called tablespaces. Each tablespace in an Oracle database consists of one or more files called datafiles, which are physical structures that conform to the operating system in which Oracle is running.

**Syntax:**
```sql
CREATE TABLESPACE <tablespace name> DATAFILE 'C:\oraclexe\app\oracle\product\10.2.0\server\<file name.dbf>' SIZE 50M;
```

**Example:**
```sql
CREATE TABLESPACE te_cs DATAFILE 'C:\oraclexe\app\oracle\product\10.2.0\server\usr.dbf' SIZE 50M;
```

#### CREATE USER:
The DBA creates user by executing CREATE USER statement. The user is someone who connects to the database if enough privilege is granted.

**Syntax:**
```sql
CREATE USER <username> -- (name of user to be created)
IDENTIFIED BY <password> -- (specifies that the user must login with this password)
```

**Example:**
```sql
CREATE USER James IDENTIFIED BY bob;
```
(The user does not have privilege at this time, it has to be granted. These privileges determine what user can do at database level.)

#### PRIVILEGES:
A privilege is a right to execute an SQL statement or to access another user's object. In Oracle, there are two types of privileges:
- **System Privileges**
- **Object Privileges**

**System Privileges:** are those through which the user can manage the performance of database actions. It is normally granted by DBA to users.
Example: Create Session, Create Table, Create user etc.

**Object Privileges:** allow access to objects or privileges on object, i.e. tables, table columns, tables, views etc. It includes alter, delete, insert, select update etc.
(After creating the user, DBA grant specific system privileges to user)

#### GRANT:
The DBA uses the GRANT statement to allocate system privileges to other user.

**Syntax:**
```sql
GRANT privilege [privilege…. … ] TO USER;
```

**Example:**
```sql
GRANT create session, create table, create view TO James;
```

Object privileges vary from object to object. An owner has all privilege or specific privileges on object.

```sql
GRANT object_priv [(column)] ON object TO user;
```

```sql
GRANT select, insert ON emp TO James;
```

```sql
GRANT select, update (e_name, e_address) ON emp TO James;
```

#### CHANGE PASSWORD:
The DBA creates an account and initializes a password for every user. You can change password by using ALTER USER statement.

**Syntax:**
```sql
ALTER USER <some user name> IDENTIFIED BY <New password>
```

**Example:**
```sql
ALTER USER James IDENTIFIED BY sam
```

#### REVOKE:
REVOKE statement is used to remove privileges granted to other users. The privileges you specify are revoked from the users.

**Syntax:**
```sql
REVOKE [privilege.. …] ON object FROM user
```

**Example:**
```sql
REVOKE create session, create table FROM James;
```

```sql
REVOKE select, insert ON emp FROM James;
```

#### ROLE:
A role is a named group of related privileges that can be granted to user. In other words, role is a predefined collection of privileges that are grouped together, thus privileges are easier to assign to users.

```sql
CREATE ROLE custom;
GRANT create table, create view TO custom;
GRANT select, insert ON emp TO custom;
```

**Example:**
```sql
GRANT custom TO James, Steve;
```

### LAB PRACTICE ASSIGNMENT:
1. Create user and implement the following commands on relation (Emp and Dept).
2. Develop a query to grant all privileges of employees table into departments table.
3. Develop a query to grant some privileges of employees table into departments table.
4. Develop a query to revoke all privileges of employees table from departments table.
5. Develop a query to revoke some privileges of employees table from departments table.
