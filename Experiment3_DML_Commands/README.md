# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

**Question 1**
```
Write a SQL query to calculate the original price using the discount percentage and the given discounted price. Return product_id, discounted_price, discount_percentage, and original_price.
Sample table: Products

product_id | discounted_price | discount_percentage
 ------------+------------------+---------------------
 101 | 45.00 | 0.10 
102 | 63.75 | 0.15 
103 | 80.00 | 0.20
```

```
SELECT product_id,discounted_price,discount_percentage,ROUND(discounted_price / (1-discount_percentage),2)AS original_price
FROM Products;
```

**Output:**
<img width="1159" height="290" alt="image" src="https://github.com/user-attachments/assets/b9041180-4338-4ab2-82ea-e4d89b20f69b" />



**Question 2**
```
Write a SQL query to find customers who are either from the city 'New York' or who have a grade greater than 200. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
```

```
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE city='New York' or grade>200;
```

**Output:**
<img width="1094" height="402" alt="image" src="https://github.com/user-attachments/assets/7d465983-f1ea-44f7-86a4-e20939f63a58" />



**Question 3**
```
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
```

```
UPDATE PRODUCTS
SET sell_price=ROUND(sell_price*1.10,2)
WHERE supplier_id=6;
```

**Output:**
<img width="1225" height="624" alt="image" src="https://github.com/user-attachments/assets/bcb4dae8-16e4-4413-b913-e73633a2ec49" />



**Question 4**
```
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
```

```
UPDATE Employees
SET hire_date='2024-01-24'
WHERE department_id=50;
```

**Output:**
<img width="1118" height="287" alt="image" src="https://github.com/user-attachments/assets/aff30af4-b30f-4751-8709-f0a3837b0432" />



**Question 5**
```
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.
 
Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
```

```
DELETE FROM customer
WHERE GRADE!=3;
```

**Output:**
<img width="694" height="488" alt="image" src="https://github.com/user-attachments/assets/03bd1b4f-23e2-443b-ba52-3b3dba778a8f" />



**Question 6**
```
write a SQL query to identify customers who do not belong to the city of 'New York' or have a grade value that exceeds 100. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
```

```
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE city!='New York' AND grade=100;
```

**Output:**
<img width="1196" height="371" alt="image" src="https://github.com/user-attachments/assets/0dc1b391-fdb7-49e9-bed1-24f7bb04ac63" />



**Question 7**
```
Write a SQL statement to change the EMAIL and COMMISSION_PCT column of the following EMPLOYEES table with 'not available' and 0.55 for those employees whose DEPARTMENT_ID is 110.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
```

```
UPDATE Employees
SET email = 'not available',
commission_pct=0.55
WHERE department_id=110;
```


**Output:**
<img width="1278" height="360" alt="image" src="https://github.com/user-attachments/assets/ace7a67b-13d8-43ee-a1c2-27b414ad25d2" />



**Question 8**
```
Write a SQL query to Retrieve the department name and location concatenated with a comma

Table name: dept
 
name        type
----------  ----------
deptno       INT
dname       VARCHAR(100)
loc         VARCHAR(100)
```

```
SELECT dname || ', ' || loc AS dept_location
FROM dept;
```

**Output:**
<img width="687" height="469" alt="image" src="https://github.com/user-attachments/assets/61503ee7-c219-49f6-b671-d0e7fbd8f9bc" />



**Question 9**
```
Write a SQL statement to Change the category to 'Household' where product name contains 'Detergent' in the products table.

Products Table 

name          type       
----------    ---------- 
product_id     INT PRIMARY KEY        
product_name   VARCHAR(10) 
category       VARCHAR(50) 
cost_price     DECIMAL(10) 
sell_price     DECIMAL(10) 
reorder_lvl    INT        
quantity       INT        
supplier_id    INT
```

```
UPDATE products
SET category='Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**
<img width="1292" height="459" alt="image" src="https://github.com/user-attachments/assets/c17a2231-574b-4aa8-ac39-acb761a4978d" />



**Question 10**
```
Write a SQL query to display hire dates in the format "DD-MM-YYYY" from the emp table

cid         name        type        
----------  ----------  ---------- 
0           empno       INT         
1           ename       VARCHAR(100)
2           job         VARCHAR(50)
3           mgr         INT        
4           hiredate    DATE        
5           sal         DECIMAL(10,2)  
6           comm        DECIMAL(10,2)  
7           deptno      INT
```

```
SELECT ename,strftime('%d-%m-%Y',hiredate) AS HireDateFormatted
From emp;
```

**Output:**
<img width="1030" height="432" alt="image" src="https://github.com/user-attachments/assets/48c7382e-bbbd-4078-b101-c37323ba808c" />



<img width="1894" height="882" alt="image" src="https://github.com/user-attachments/assets/3a0c015e-ffa5-4a4f-99fe-a17c57119154" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
