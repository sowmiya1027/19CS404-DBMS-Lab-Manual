# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
<img width="1031" height="367" alt="image" src="https://github.com/user-attachments/assets/6fb582d3-9bb6-4d3c-8407-fd02708c6ff2" />

```
select * from CUSTOMERS 
where ADDRESS='Delhi';
```

**Output:**

<img width="1221" height="422" alt="image" src="https://github.com/user-attachments/assets/05cd8d71-ba45-418a-8739-99c95e51a4c0" />



**Question 2**
<img width="1245" height="350" alt="image" src="https://github.com/user-attachments/assets/6dee6f5c-2285-4aa0-924e-c6e317f11b7f" />

```
select ord_no,purch_amt,ord_date,customer_id,salesman_id from ORDERS
where purch_amt>(
select AVG(purch_amt)
from ORDERS
where ord_date='2012-10-10'
);
```

**Output:**
<img width="1259" height="469" alt="image" src="https://github.com/user-attachments/assets/aacc149b-c08e-46b9-80c3-9cedbce269ef" />



**Question 3**
<img width="1007" height="268" alt="image" src="https://github.com/user-attachments/assets/6cd92ea1-f9c7-4446-a82a-49fb39f6cbcb" />

```
select * from Medications
where dosage=(select MAX(dosage) from Medications);
```

**Output:**
<img width="1093" height="431" alt="image" src="https://github.com/user-attachments/assets/7dcf0215-4764-402c-8bb4-b9e66fa84898" />



**Question 4**
<img width="1195" height="350" alt="image" src="https://github.com/user-attachments/assets/4a81813b-17b7-4a36-9ec3-4f8caa3f8528" />

```
select * from GRADES g1
where grade=(select MIN(grade) from GRADES g2 where g2.subject=g1.subject);
```

**Output:**

<img width="1259" height="442" alt="image" src="https://github.com/user-attachments/assets/f5b0a62c-9cee-4c70-8e6d-e1e6ccdb1a8c" />


**Question 5**
<img width="1027" height="326" alt="image" src="https://github.com/user-attachments/assets/b2c56c24-d709-4499-a8af-b5c0fcc8ddfa" />

```
select * from CUSTOMERS
where SALARY>4500;
```

**Output:**

<img width="1247" height="402" alt="image" src="https://github.com/user-attachments/assets/dc3266a4-d799-4bcd-84e8-4f1c38ab9a8e" />


**Question 6**
<img width="1015" height="242" alt="image" src="https://github.com/user-attachments/assets/55cf1573-335f-42c3-8d59-d5e558485273" />

```
select * from customer
where city!=(
select city from customer
where id=(select MAX(id) from customer)
);
```

**Output:**
<img width="1266" height="479" alt="image" src="https://github.com/user-attachments/assets/b3ae3875-b468-4b5c-933a-9e51f8205d2d" />


**Question 7**
<img width="1009" height="321" alt="image" src="https://github.com/user-attachments/assets/6d53b0fc-0607-4292-882d-901757612587" />

```
select * from CUSTOMERS
where SALARY<2500;
```

**Output:**
<img width="1248" height="461" alt="image" src="https://github.com/user-attachments/assets/b44fb411-342e-4d60-aba7-5113b4e86f37" />



**Question 8**
<img width="1263" height="399" alt="image" src="https://github.com/user-attachments/assets/e4d83899-ae84-4f5f-bc78-1c71bf33c791" />

```
select ord_no,purch_amt,ord_date,customer_id,salesman_id from Orders
where salesman_id IN(
select salesman_id from Salesman where city='London');
```

**Output:**
<img width="1254" height="401" alt="image" src="https://github.com/user-attachments/assets/2e6ce5ae-6181-4e9e-960a-fb37ec35df8a" />


**Question 9**
<img width="1068" height="429" alt="image" src="https://github.com/user-attachments/assets/9c5c8db3-ab8a-4ba6-b055-ce938316a20c" />

```
select commission from salesman 
where salesman_id IN(
select salesman_id from customer where city='Paris');
```

**Output:**

<img width="1027" height="365" alt="image" src="https://github.com/user-attachments/assets/497b18e2-9844-4342-bef7-71eac9fd26ac" />


**Question 10**
<img width="1210" height="300" alt="image" src="https://github.com/user-attachments/assets/81ff8015-8498-4c5c-aaca-4a77fdb9dbe6" />

```
select name,city from customer
where city IN(
select city from customer where id IN(3,7));
```

**Output:**

<img width="1171" height="492" alt="image" src="https://github.com/user-attachments/assets/2abb209d-a907-406f-861b-d20a04820a83" />


<img width="1919" height="971" alt="image" src="https://github.com/user-attachments/assets/ae1cd255-df72-4ca5-862b-53ee41f388cc" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
