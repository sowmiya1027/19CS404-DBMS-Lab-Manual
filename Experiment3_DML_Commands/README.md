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
<img width="1095" height="294" alt="image" src="https://github.com/user-attachments/assets/cf2afffe-16d1-4ef5-a7de-d70cdb0c3147" />

```
SELECT product_id,discounted_price,discount_percentage,ROUND(discounted_price / (1-discount_percentage),2)AS original_price
FROM Products;
```

**Output:**
<img width="1159" height="290" alt="image" src="https://github.com/user-attachments/assets/b9041180-4338-4ab2-82ea-e4d89b20f69b" />



**Question 2**
<img width="1137" height="247" alt="image" src="https://github.com/user-attachments/assets/125bceda-9fa0-4fb5-926b-13586a5f18b5" />

```
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE city='New York' or grade>200;
```

**Output:**
<img width="1094" height="402" alt="image" src="https://github.com/user-attachments/assets/7d465983-f1ea-44f7-86a4-e20939f63a58" />



**Question 3**
<img width="854" height="352" alt="image" src="https://github.com/user-attachments/assets/4ee3d572-b8cb-4034-ab20-dc5bd1419a0f" />

```
UPDATE PRODUCTS
SET sell_price=ROUND(sell_price*1.10,2)
WHERE supplier_id=6;
```

**Output:**
<img width="1225" height="624" alt="image" src="https://github.com/user-attachments/assets/bcb4dae8-16e4-4413-b913-e73633a2ec49" />



**Question 4**
<img width="784" height="395" alt="image" src="https://github.com/user-attachments/assets/9926748c-be0d-4fb2-af5d-4823c3be0c49" />

```
UPDATE Employees
SET hire_date='2024-01-24'
WHERE department_id=50;
```

**Output:**
<img width="1118" height="287" alt="image" src="https://github.com/user-attachments/assets/aff30af4-b30f-4751-8709-f0a3837b0432" />



**Question 5**
<img width="1219" height="223" alt="image" src="https://github.com/user-attachments/assets/63d47567-ad98-4de7-bf65-1913862ac599" />

```
DELETE FROM customer
WHERE GRADE!=3;
```

**Output:**
<img width="694" height="488" alt="image" src="https://github.com/user-attachments/assets/03bd1b4f-23e2-443b-ba52-3b3dba778a8f" />



**Question 6**
<img width="1257" height="315" alt="image" src="https://github.com/user-attachments/assets/4f810a75-0414-4ab0-b8a2-c23d56ddb0b9" />

```
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE city!='New York' AND grade=100;
```

**Output:**
<img width="1196" height="371" alt="image" src="https://github.com/user-attachments/assets/0dc1b391-fdb7-49e9-bed1-24f7bb04ac63" />



**Question 7**
<img width="1149" height="330" alt="image" src="https://github.com/user-attachments/assets/af735cfb-d17e-47ad-9f25-514b4b1427d5" />

```
UPDATE Employees
SET email = 'not available',
commission_pct=0.55
WHERE department_id=110;
```


**Output:**
<img width="1278" height="360" alt="image" src="https://github.com/user-attachments/assets/ace7a67b-13d8-43ee-a1c2-27b414ad25d2" />



**Question 8**
<img width="686" height="184" alt="image" src="https://github.com/user-attachments/assets/0fd6d683-275b-4e53-8515-646cdeffc399" />

```
SELECT dname || ', ' || loc AS dept_location
FROM dept;
```

**Output:**
<img width="687" height="469" alt="image" src="https://github.com/user-attachments/assets/61503ee7-c219-49f6-b671-d0e7fbd8f9bc" />



**Question 9**
<img width="881" height="273" alt="image" src="https://github.com/user-attachments/assets/3195dce8-bf69-44a1-a3ed-af67db0f25d7" />

```
UPDATE products
SET category='Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**
<img width="1292" height="459" alt="image" src="https://github.com/user-attachments/assets/c17a2231-574b-4aa8-ac39-acb761a4978d" />



**Question 10**
<img width="614" height="238" alt="image" src="https://github.com/user-attachments/assets/68fd5eab-2051-4c05-ab46-aa9356495eaa" />

```
SELECT ename,strftime('%d-%m-%Y',hiredate) AS HireDateFormatted
From emp;
```

**Output:**
<img width="640" height="360" alt="image" src="https://github.com/user-attachments/assets/e12e2878-2e0a-4393-bd61-44c143e96a18" />


<img width="1894" height="882" alt="image" src="https://github.com/user-attachments/assets/3a0c015e-ffa5-4a4f-99fe-a17c57119154" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
