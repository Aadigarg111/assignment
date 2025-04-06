# Experiment No: 9
## Title: 
- Study and Implementation of Database Backup & Recovery Commands.
- Study and Implementation of Rollback, Commit, Save point.

### Objective:
To understand the concept of administrative commands

### Theory:

A transaction is a logical unit of work. All changes made to the database can be referred to as a transaction. Transaction changes can be made permanent to the database only if they are committed. A transaction begins with an executable SQL statement & ends explicitly with either rollback or commit statement.

1. **COMMIT:**
This command is used to end a transaction. Only with the help of the commit command, transaction changes can be made permanent to the database.

**Syntax:**
```sql
COMMIT;
```

**Example:**
```sql
COMMIT;
```

2. **SAVE POINT:**
Save points are like marks to divide a very lengthy transaction to smaller ones. They are used to identify a point in a transaction to which we can later roll back. Thus, save point is used in conjunction with rollback.

**Syntax:**
```sql
SAVEPOINT ID;
```

**Example:**
```sql
SAVEPOINT xyz;
```

3. **ROLLBACK:**
A rollback command is used to undo the current transactions. We can roll back the entire transaction so that all changes made by SQL statements are undone, or roll back a transaction to a savepoint so that the SQL statements after the savepoint are rolled back.

**Syntax:**
```sql
ROLLBACK;  -- current transaction can be rolled back
ROLLBACK TO SAVEPOINT ID;
```

**Example:**
```sql
ROLLBACK;
ROLLBACK TO SAVEPOINT xyz;
```

### LAB PRACTICE ASSIGNMENT:
1. Write a query to implement the save point.
2. Write a query to implement the rollback.
3. Write a query to implement the commit.
