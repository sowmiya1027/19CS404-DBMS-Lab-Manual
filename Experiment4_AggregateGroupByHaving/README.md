# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
<img width="880" height="260" alt="image" src="https://github.com/user-attachments/assets/672e21e6-8374-43fc-b2aa-41d18897a508" />

```
SELECT COUNT(*) AS employees_count from employee
where income>50000;
```

**Output:**
<img width="958" height="400" alt="image" src="https://github.com/user-attachments/assets/42c8beb3-a9f9-49ac-9b55-c9da5040b5fb" />



**Question 2**
<img width="730" height="264" alt="image" src="https://github.com/user-attachments/assets/9597693c-4b69-47e3-890b-f854f241499e" />

```
select name,LENGTH(name) as length from customer
order by LENGTH(name) DESC
LIMIT 1;
```

**Output:**
<img width="1002" height="370" alt="image" src="https://github.com/user-attachments/assets/0cd86782-8b93-49dc-88f4-e5eceea658af" />



**Question 3**
<img width="1095" height="271" alt="image" src="https://github.com/user-attachments/assets/fa917af3-3e2b-4a6d-b11d-dfb940ade193" />

```
select MAX(age)-MIN(age) AS age_difference
from employee;
```

**Output:**
<img width="1264" height="521" alt="image" src="https://github.com/user-attachments/assets/748e0e02-b053-43a5-9036-99998ed1664c" />



**Question 4**
<img width="1104" height="259" alt="image" src="https://github.com/user-attachments/assets/1a3e66a9-c9b8-4ffb-86c8-3c560be70326" />

```
select DoctorID,COUNT(*) as TotalAppointments from Appointments
GROUP BY DoctorID;
```

**Output:**
<img width="1181" height="718" alt="image" src="https://github.com/user-attachments/assets/ae725a14-6d89-4818-af85-7252742ff001" />



**Question 5**
<img width="1094" height="226" alt="image" src="https://github.com/user-attachments/assets/f22f136c-916b-47ea-b6c7-5f5ec39039a1" />

```
select DoctorID,COUNT(*) as TotalPrescriptions from Prescriptions 
Group by DoctorID;
```

**Output:**
<img width="1143" height="814" alt="image" src="https://github.com/user-attachments/assets/2277eaaf-b6df-4bfb-802f-ca75ccd20779" />



**Question 6**
<img width="1061" height="243" alt="image" src="https://github.com/user-attachments/assets/6346fddd-b98c-429c-a11a-2299e4f4ad21" />

```
select Diagnosis,COUNT(*) as DiagnosisCount from MedicalRecords
group by Diagnosis
order by DiagnosisCount desc
limit 1;
```

**Output:**

<img width="1172" height="399" alt="image" src="https://github.com/user-attachments/assets/906def77-76d4-4da7-965f-5df27eeb9adc" />



**Question 7**
<img width="1220" height="297" alt="image" src="https://github.com/user-attachments/assets/7c7e115e-3533-4ff8-9238-b57dd229fc43" />

```
select age,MIN(Income) as Income from employee 
group by age
having MIN(Income)<1000000;
```

**Output:**

<img width="1028" height="502" alt="image" src="https://github.com/user-attachments/assets/d53295c5-40db-4100-a126-809bd25fa0b8" />



**Question 8**
<img width="1239" height="268" alt="image" src="https://github.com/user-attachments/assets/710b4f84-3c76-4fc0-be52-4be7efb2915d" />

```
select (age/5)*5 as age_group,MIN(age) from customer1
group by (age/5)*5
having MIN(age)<25;
```

**Output:**
<img width="925" height="389" alt="image" src="https://github.com/user-attachments/assets/c3f12e03-5609-417e-afd7-a9d36cc0edfe" />



**Question 9**
<img width="1240" height="285" alt="image" src="https://github.com/user-attachments/assets/3a54280f-fe11-411a-a259-a234a95da71d" />

```
select city,SUM(income) as Income from employee
group by city
having SUM(income)>200000;
```

**Output:**
<img width="1003" height="598" alt="image" src="https://github.com/user-attachments/assets/dcca448d-93cf-4386-bf9d-8c6bacba7567" />



**Question 10**
<img width="1029" height="237" alt="image" src="https://github.com/user-attachments/assets/4e309ecf-303f-4efe-ac7f-ed51735d177d" />

```
select address,AVG(salary) from customer1
group by address
having AVG(salary)<15000;
```
**Output:**

<img width="1089" height="670" alt="image" src="https://github.com/user-attachments/assets/52434156-e804-4e40-b15e-23584ab20802" />


<img width="1917" height="959" alt="Screenshot 2026-08-24 091208" src="https://github.com/user-attachments/assets/95b3c611-36bb-4720-b8c8-2cd053b420aa" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
