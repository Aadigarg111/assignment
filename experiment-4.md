# Experiment No: 4 - Implementation of Different Types of Operators in SQL

## Objective
- To learn and implement different types of SQL operators
- To understand how operators can be used in database queries

## Types of SQL Operators

### 1. Arithmetic Operators
- **+** (Addition): Adds values on either side of the operator
- **-** (Subtraction): Subtracts right hand operand from left hand operand
- **\*** (Multiplication): Multiplies values on either side of the operator
- **/** (Division): Divides left hand operand by right hand operand
- **^** (Power): Raises to power of
- **%** (Modulus): Divides left hand operand by right hand operand and returns remainder

### 2. Logical Operators
- **AND**: Allows multiple conditions in a WHERE clause (all conditions must be true)
  - Example: `WHERE salary > 5000 AND dept_id = 10`
- **OR**: Combines multiple conditions in a WHERE clause (any condition can be true)
  - Example: `WHERE salary > 5000 OR dept_id = 10`
- **NOT**: Reverses the meaning of the logical operator
  - Examples: NOT EXISTS, NOT BETWEEN, NOT IN

### 3. Comparison Operators
- **=**: Equal to
- **!=** or **<>**: Not equal to
- **>**: Greater than
- **<**: Less than
- **>=**: Greater than or equal to
- **<=**: Less than or equal to

### 4. Special Operators

- **BETWEEN**: Searches values within a range
  ```sql
  SELECT * FROM employees WHERE salary BETWEEN 50000 AND 100000;
  ```

- **IS NULL**: Compares a value with NULL attribute
  ```sql
  SELECT * FROM employees WHERE manager_id IS NULL;
  ```

- **ALL**: Compares a value to all values in another value set
  ```sql
  SELECT * FROM employees WHERE salary > ALL (SELECT salary FROM employees WHERE dept_id = 20);
  ```

- **ANY**: Compares a value to any applicable value in the list
  ```sql
  SELECT * FROM employees WHERE salary > ANY (SELECT salary FROM employees WHERE dept_id = 30);
  ```

- **LIKE**: Compares a value to similar values using wildcards
  - % (percent) represents zero, one, or multiple characters
  - _ (underscore) represents a single character
  ```sql
  SELECT * FROM employees WHERE last_name LIKE 'S%';  -- Names starting with S
  SELECT * FROM employees WHERE last_name LIKE '_mith';  -- Names like Smith
  ```

- **IN**: Compares a value to a list of specified values
  ```sql
  SELECT * FROM employees WHERE dept_id IN (10, 20, 30);
  ```

- **EXISTS**: Checks for the existence of rows returned by a subquery
  ```sql
  SELECT * FROM departments d WHERE EXISTS (SELECT * FROM employees e WHERE e.dept_id = d.dept_id);
  ```

### 5. Set Operators
Combine results of two queries into a single result set:

- **UNION**: Returns all distinct rows selected by either query
  ```sql
  SELECT emp_id FROM employees UNION SELECT emp_id FROM retired_employees;
  ```

- **UNION ALL**: Returns all rows from both queries, including duplicates
  ```sql
  SELECT emp_id FROM employees UNION ALL SELECT emp_id FROM retired_employees;
  ```

- **INTERSECT**: Returns rows that are common to both queries
  ```sql
  SELECT emp_id FROM employees INTERSECT SELECT emp_id FROM project_members;
  ```

- **MINUS**: Returns rows from first query that are not in second query
  ```sql
  SELECT emp_id FROM employees MINUS SELECT emp_id FROM project_members;
  ```

## Practice Assignment
Write SQL queries for:

1. Display all the dept numbers available with the dept and emp tables avoiding duplicates
2. Display all the dept numbers available with the dept and emp tables
3. Display all the dept numbers available in emp and not in dept tables and vice versa
