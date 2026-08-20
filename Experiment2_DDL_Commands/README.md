# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
```
Insert the following products into the Products table:

Name        Category     Price       Stock
----------  -----------  ----------  ----------
Smartphone  Electronics  800         150
Headphones  Accessories  200         300
```

```
INSERT INTO Products(Name,Category,Price,Stock)
VALUES('Smartphone','Electronics',800,150),
('Headphones','Accessories',200,300);
```

**Output:**
<img width="1236" height="432" alt="image" src="https://github.com/user-attachments/assets/9788117c-a639-4013-8d5a-f30f1e81bc24" />



**Question 2**
Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).

```
CREATE TABLE Orders
(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY (CustomerID)
REFERENCES Customers(CustomerID)
);
```

**Output:**
<img width="1240" height="376" alt="image" src="https://github.com/user-attachments/assets/2b9636a7-4b3f-427a-a537-f0aeabac71f4" />



**Question 3**
Insert all customers from Old_customers into Customers
Table attributes are CustomerID, Name, Address, Email

```
INSERT INTO Customers(CustomerID,Name,Address,Email)
SELECT CustomerID,Name,Address,Email FROM Old_customers;
```

**Output:**
<img width="1237" height="366" alt="image" src="https://github.com/user-attachments/assets/9061b282-9ccb-41d5-92d3-2afc6e845c99" />



**Question 4**
```
In the Employee table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

EmployeeID  Name          Position    Department  Salary
----------  ------------  ----------  ----------  ----------
5           George Clark  Consultant
7           Noah Davis    Manager     HR          60000
8           Ava Miller    Consultant  IT
```

```
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES
(5,'George Clark','Consultant',NULL,NULL),
(7,'Noah Davis','Manager','HR',60000),
(8,'Ava Miller','Consultant','IT',NULL);
```

**Output:**
<img width="1233" height="378" alt="image" src="https://github.com/user-attachments/assets/83e59575-6bfe-4f59-8344-5655332db558" />



**Question 5**
Write an SQL query to change the name of the column id to employee_id in the table employee.

```
ALTER TABLE employee RENAME id TO employee_id;
```

**Output:**
<img width="1227" height="331" alt="image" src="https://github.com/user-attachments/assets/c8c013da-e692-4eb3-a7c0-3dd1d2a09aae" />



**Question 6**
Create a table named Reviews with the following columns:

ReviewID as INTEGER
ProductID as INTEGER
Rating as REAL
ReviewText as TEXT

```
CREATE TABLE Reviews
(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT
);
```

**Output:**
<img width="1235" height="489" alt="image" src="https://github.com/user-attachments/assets/1c381f06-18c5-4252-855e-c5bf9e403248" />



**Question 7**
Create a table named Members with the following columns:

MemberID as INTEGER
MemberName as TEXT
JoinDate as DATE

```
CREATE TABLE Members
(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE
);
```

**Output:**
<img width="1235" height="459" alt="image" src="https://github.com/user-attachments/assets/19de0ef0-2353-4222-85b2-4f70fe7893ad" />



**Question 8**
Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
DueDate as DATE should be greater than the InvoiceDate.
Amount as REAL should be greater than 0.

```
CREATE Table Invoices
(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE,
Amount REAL,
CHECK (DueDate > InvoiceDate),
CHECK (Amount > 0)
);
```

**Output:**
<img width="1231" height="379" alt="image" src="https://github.com/user-attachments/assets/46db5e46-71c1-4ec0-80b7-9721da0257a7" />



**Question 9**
Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.

```
CREATE table Bonuses
(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL,
BonusDate DATE,
Reason TEXT NOT NULL,
Foreign key (EmployeeID)
REFERENCES Employees(EmployeeID),
CHECK(BonusAmount > 0)
);
```

**Output:**
<img width="1238" height="367" alt="image" src="https://github.com/user-attachments/assets/f06ecfc6-7540-4b23-94f9-2c0820b4a8a3" />



**Question 10**
Write a SQL Query  to add attribute ISBN as varchar(30) and domain_dept as varchar(30) in the table 'books'

```
ALTER TABLE books ADD COLUMN ISBN varchar(30);
ALTER TABLE books ADD COLUMN domain_dept varchar(30);
```

**Output:**
<img width="1244" height="467" alt="image" src="https://github.com/user-attachments/assets/8582a100-d439-470c-8aac-737b25e3323a" />



<img width="1859" height="912" alt="image" src="https://github.com/user-attachments/assets/2d76f51f-d779-43c6-9f10-361ce1cb7ea0" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
