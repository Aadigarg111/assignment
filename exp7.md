# Experiment No: 7
## Title: Study & Implementation of
- Sub queries
- Views

### Objective:
- To perform nested Queries and joining Queries using DML command
- To understand the implementation of views.

### Theory:

#### SUBQUERIES:
The query within another is known as a sub query. A statement containing sub query is called parent statement. The rows returned by sub query are used by the parent statement or in other words A subquery is a SELECT statement that is embedded in a clause of another SELECT statement.

You can place the subquery in a number of SQL clauses:
- WHERE clause
- HAVING clause
- FROM clause
- OPERATORS (IN, ANY, ALL, <, >, >=, <= etc.)

**Types:**
1. **Sub queries that return several values:** Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
2. **Multiple queries:** Here more than one sub query is used. These multiple sub queries are combined by means of 'and' & 'or' keywords.
3. **Correlated sub query:** A sub query is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

#### VIEW:
In SQL, a view is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.

A view is a virtual table, which consists of a set of columns from one or more tables. It is similar to a table but it does not store in the database. View is a query stored as an object.

**Syntax:**
```sql
CREATE VIEW <view_name> AS SELECT <set of fields>
FROM relation_name WHERE (Condition)
```

**Example:**
```sql
CREATE VIEW employee AS SELECT empno, ename, job FROM EMP
WHERE job = 'clerk';
```

**Another Example:**
```sql
CREATE VIEW [Current Product List] AS
SELECT ProductID, ProductName
FROM Products
WHERE Discontinued=No;
```

#### UPDATING A VIEW:
A view can be updated by using the following syntax:

**Syntax:**
```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition
```

#### DROPPING A VIEW:
A view can be deleted with the DROP VIEW command.

**Syntax:**
```sql
DROP VIEW <view_name>;
```

### LAB PRACTICE ASSIGNMENT:
Consider the following schema:
- Sailors (sid, sname, rating, age)
- Boats (bid, bname, color)
- Reserves (sid, bid, day(date))

Write subquery statement for the following queries:
1. Find all information of sailors who have reserved boat number 101.
2. Find the name of boat reserved by Bob.
3. Find the names of sailors who have reserved a red boat, and list in the order of age.
4. Find the names of sailors who have reserved at least one boat.
5. Find the ids and names of sailors who have reserved two different boats on the same day.
6. Find the ids of sailors who have reserved a red boat or a green boat.
7. Find the name and the age of the youngest sailor.
8. Count the number of different sailor names.
9. Find the average age of sailors for each rating level.
10. Find the average age of sailors for each rating level that has at least two sailors.
