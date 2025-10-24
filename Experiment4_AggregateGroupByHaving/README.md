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
--
<img width="993" height="471" alt="image" src="https://github.com/user-attachments/assets/ef533d35-b9b6-4812-92fc-bea8654800a2" />


```
SELECT Address,COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

<img width="1226" height="476" alt="image" src="https://github.com/user-attachments/assets/a5938828-8e7a-46ed-aebc-75f85dec91cb" />

**Question 2**
---
<img width="1017" height="550" alt="image" src="https://github.com/user-attachments/assets/53e617a2-cd27-4b66-b654-799d1d8a9844" />


```
SELECT Specialty,Gender,COUNT(*) AS TotalDoctors
FROM Doctors 
GROUP BY Specialty,Gender;
```

**Output:**

<img width="1222" height="718" alt="image" src="https://github.com/user-attachments/assets/56fbf191-0d98-4098-92d2-f08a3d830793" />


**Question 3**
---
<img width="669" height="632" alt="image" src="https://github.com/user-attachments/assets/9bb5fab7-a2dc-4702-b801-76e4fcb25f5b" />


```
SELECT strftime('%H', AppointmentDateTime) AS HourOfDay,COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY HourOfDay;
```

**Output:**

<img width="1224" height="596" alt="image" src="https://github.com/user-attachments/assets/b797c75d-d6e9-4906-9547-378dc2bfd25f" />


**Question 4**
---
<img width="851" height="477" alt="image" src="https://github.com/user-attachments/assets/a18dd429-392a-4263-8f43-e3ee665a7163" />


```
SELECT AVG(income) AS avg_income
FROM employee
WHERE name LIKE 'A%';
```

**Output:**

<img width="423" height="375" alt="image" src="https://github.com/user-attachments/assets/55e6e14c-f97c-40f7-bc35-a36b4b8ce011" />


**Question 5**
---
<img width="941" height="491" alt="image" src="https://github.com/user-attachments/assets/2b3fc5e3-8537-4470-a8dd-2be4cffd2b8a" />


```
SELECT AVG(purch_amt) AS AVERAGE
FROM orders;
```

**Output:**

<img width="375" height="388" alt="image" src="https://github.com/user-attachments/assets/5aae1226-6262-4870-b424-3d4c6cef8cfe" />

**Question 6**
---
<img width="1138" height="487" alt="image" src="https://github.com/user-attachments/assets/873d89f5-cc78-4fef-ad68-b11ca221e013" />


```
SELECT SUM(workhour) AS "Total working hours"
FROM employee1;
```

**Output:**

<img width="552" height="367" alt="image" src="https://github.com/user-attachments/assets/3cf4e117-d53e-4839-8bbd-5fd67abed8df" />


**Question 7**
---
<img width="760" height="506" alt="image" src="https://github.com/user-attachments/assets/073f5cfe-1d7a-4866-991d-40878c3ca9bc" />


```
SELECT COUNT(*) AS "COUNT"
FROM customer;
```

**Output:**

<img width="395" height="385" alt="image" src="https://github.com/user-attachments/assets/4563b1ef-2ebf-4509-ad8c-76458e4d1e1a" />

**Question 8**
---
<img width="1197" height="460" alt="image" src="https://github.com/user-attachments/assets/dc9594de-2e2b-4a0e-b5ec-b49c658b3843" />


```
SELECT address, AVG(salary) AS "AVG(salary)"
FROM customer1
GROUP BY address
HAVING AVG(salary)>5000;
```

**Output:**

<img width="580" height="504" alt="image" src="https://github.com/user-attachments/assets/0a3519ae-2928-40e2-afaa-e3cd560db7ab" />


**Question 9**
---
<img width="1207" height="475" alt="image" src="https://github.com/user-attachments/assets/be85a2a1-74e8-42cb-bade-82729802b090" />


```
SELECT (age/5)*5 AS age_group,SUM(salary) AS "SUM(salary)"
FROM customer1
GROUP BY (age/5)*5
HAVING SUM(salary) > 5000;
```

**Output:**

<img width="593" height="422" alt="image" src="https://github.com/user-attachments/assets/415fcb1a-82f9-4f13-b734-d992e49a5724" />


**Question 10**
---
<img width="1158" height="478" alt="image" src="https://github.com/user-attachments/assets/4ff86eb9-784b-49c8-a0cf-c41125bba006" />


```
SELECT category_id,SUM(price) AS Total_Cost
FROM products
GROUP BY category_id
HAVING SUM(price) > 50;
```

**Output:**

<img width="579" height="396" alt="image" src="https://github.com/user-attachments/assets/9cf40c5f-82c7-4c94-8e6d-e0b86d3d0c32" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
