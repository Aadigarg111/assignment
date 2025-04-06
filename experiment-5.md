# Experiment No: 5 - Implementation of Different Types of Joins

## Objective
- To understand and implement different types of SQL joins
- To learn how to combine data from multiple related tables

## Theory
The SQL JOIN clause is used to combine records from two or more tables in a database. A JOIN is a means for combining fields from two tables by using values common to each. The join operation is typically performed in the WHERE clause, which combines specified rows of tables.

## Basic JOIN Syntax
```sql
SELECT column1, column2, column3...
FROM table_name1, table_name2
WHERE table_name1.column_name = table_name2.column_name;
```

## Types of Joins

### 1. Simple Join
The most common type of join that retrieves rows from two tables having a common column.

#### Equi-join
A join based on equality between columns.
```sql
SELECT * FROM item, cust 
WHERE item.id = cust.id;
```

In this example, the join is performed where item.id equals cust.id, retrieving matching rows from both tables.

#### Non-Equi-join
Specifies relationships between columns using operators other than equals (=).
```sql
SELECT * FROM item, cust 
WHERE item.id < cust.id;
```

### 2. Self Join
Joining a table to itself. This allows comparison of rows within the same table.
```sql
SELECT * FROM emp x, emp y 
WHERE x.salary >= (SELECT AVG(salary) FROM emp 
                  WHERE deptno = y.deptno);
```

### 3. Outer Join
Extends the result of a simple join by including rows that don't have matching values.

#### Left Outer Join
Returns all rows from the left table and matching rows from the right table.
```sql
SELECT * FROM table1, table2 
WHERE table1.column = table2.column(+);
```

#### Right Outer Join
Returns all rows from the right table and matching rows from the left table.
```sql
SELECT * FROM table1, table2 
WHERE table1.column(+) = table2.column;
```

#### Full Outer Join
Returns all rows when there is a match in either the left or right table.

### Table Aliases
Used to make multiple table queries shorter and more readable.
```sql
SELECT e.emp_name, d.dept_name 
FROM employees e, departments d 
WHERE e.dept_id = d.dept_id;
```

## Practice Assignment
Consider the following schema:
- Sailors (sid, sname, rating, age)
- Boats (bid, bname, color)
- Reserves (sid, bid, day(date))

Write SQL queries for:
1. Find all information of sailors who have reserved boat number 101
2. Find the name of boat reserved by Bob
3. Find the names of sailors who have reserved a red boat, and list in the order of age
4. Find the names of sailors who have reserved at least one boat
5. Find the ids and names of sailors who have reserved two different boats on the same day
6. Find the ids of sailors who have reserved a red boat or a green boat
7. Find the name and the age of the youngest sailor
8. Count the number of different sailor names
9. Find the average age of sailors for each rating level
10. Find the average age of sailors for each rating level that has at least two sailors
