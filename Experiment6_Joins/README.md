# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
<img width="1250" height="573" alt="image" src="https://github.com/user-attachments/assets/78f9b1a5-9062-40cb-a1cf-6fff3260d0da" />

```
SELECT patients.first_name,surgeries. * from patients
INNER JOIN surgeries ON patients.patient_id=surgeries.patient_id
where patients.date_of_birth>'1990-01-01';
```

**Output:**
<img width="1253" height="370" alt="image" src="https://github.com/user-attachments/assets/5e43c97e-7302-4434-8092-3f4506118a50" />


**Question 2**
<img width="1266" height="386" alt="image" src="https://github.com/user-attachments/assets/476403eb-28cf-444d-b40d-3081574b3f16" />

```
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt from customer AS c
LEFT JOIN orders AS o ON c.customer_id=o.customer_id
where c.city='London';
```

**Output:**
<img width="1257" height="475" alt="image" src="https://github.com/user-attachments/assets/8eb39dc4-07aa-4be9-95cd-e8c3994f8097" />



**Question 3**
<img width="1271" height="411" alt="image" src="https://github.com/user-attachments/assets/e8f3de90-99d6-4170-bbce-5ea0e39bb249" />

```
select p.first_name AS patient_name,t.* from patients AS p
INNER JOIN test_results AS t ON p.patient_id=t.patient_id
where p.admission_date BETWEEN '2024-01-01' and '2024-01-31';
```

**Output:**
<img width="1259" height="421" alt="image" src="https://github.com/user-attachments/assets/c9fcc6fc-3f04-41c4-b6e1-23e606b86984" />


**Question 4**
<img width="1285" height="520" alt="image" src="https://github.com/user-attachments/assets/942dd616-7130-4961-9b6c-741e170fb2d1" />

```
select c.cust_name AS 'Customer Name',c.city,s.name AS Salesman,s.commission from customer c
JOIN salesman s ON c.salesman_id=s.salesman_id;
```

**Output:**
<img width="1234" height="845" alt="image" src="https://github.com/user-attachments/assets/c9f27532-3160-4ed0-9a9c-1c5f37684b0f" />


**Question 5**
<img width="1289" height="782" alt="image" src="https://github.com/user-attachments/assets/ede14baa-d96a-4b79-bd82-4aa557470cf8" />

```
select * from orders
NATURAL JOIN customer
NATURAL JOIN salesman;
```

**Output:**
<img width="1287" height="471" alt="image" src="https://github.com/user-attachments/assets/9a3c407e-9619-4fdf-a443-30ef707bbf5b" />



**Question 6**
<img width="1287" height="343" alt="image" src="https://github.com/user-attachments/assets/057d00b1-3aa3-47c9-8898-276fce18dabf" />

```
select p.first_name AS patient_name,a.* from patients as p
INNER JOIN appointments as a ON p.patient_id=a.patient_id;
```

**Output:**
<img width="1280" height="458" alt="image" src="https://github.com/user-attachments/assets/5895ebd7-9a78-4551-bb1a-0e67b197177d" />



**Question 7**
<img width="1288" height="337" alt="image" src="https://github.com/user-attachments/assets/b2318af5-5fe2-4b63-b96b-28e629212074" />

```
select c.cust_name,o.ord_no,o.ord_date,o.purch_amt from customer AS c
INNER JOIN orders  AS o ON c.customer_id=o.customer_id
where o.purch_amt>1000;
```

**Output:**
<img width="1265" height="559" alt="image" src="https://github.com/user-attachments/assets/ff0d3b6f-4043-4c10-8db1-c519b2ea1dd8" />


**Question 8**
<img width="1287" height="345" alt="image" src="https://github.com/user-attachments/assets/f350a7b9-97be-43ea-9602-b0b6da4ac799" />

```
select p.first_name AS patient_name,d.first_name AS doctor_name from patients AS p
INNER JOIN doctors AS d ON p.doctor_id=d.doctor_id
where p.discharge_date IS NULL;
```

**Output:**
<img width="1065" height="438" alt="image" src="https://github.com/user-attachments/assets/ed533592-7afa-45f9-8f15-784d33b3fabd" />


**Question 9**
<img width="1212" height="387" alt="image" src="https://github.com/user-attachments/assets/84a846e0-0612-40b3-9f61-55d58aec1558" />

```
select p.first_name AS patient_name,t.* from patients AS p
INNER JOIN test_results AS t ON p.patient_id=t.patient_id;
```

**Output:**
<img width="1264" height="490" alt="image" src="https://github.com/user-attachments/assets/f6ea1c7d-2737-4e96-9097-fa4c5f0d95e1" />


**Question 10**
<img width="1273" height="376" alt="image" src="https://github.com/user-attachments/assets/2e186aca-33b5-4aa7-8eb4-0ff74d95b0ce" />

```
select p.* from patients AS p
INNER JOIN test_results AS t ON p.patient_id=t.patient_id
where t.test_name='X-Ray' and t.result='Normal';
```

**Output:**
<img width="1248" height="417" alt="image" src="https://github.com/user-attachments/assets/7ec73167-8910-4cc8-9a30-15521ae58e28" />


<img width="1912" height="960" alt="image" src="https://github.com/user-attachments/assets/7af8f2c8-a0e6-4215-9e71-604f85bb43b9" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
