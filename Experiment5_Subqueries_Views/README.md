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
--
<img width="1007" height="721" alt="image" src="https://github.com/user-attachments/assets/350f9f99-4581-4807-a406-9dbf23cdf4f0" />


```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);
```

**Output:**

<img width="1270" height="372" alt="image" src="https://github.com/user-attachments/assets/a3204203-a266-4c59-8a60-c54565e526f3" />


**Question 2**
---
<img width="1266" height="488" alt="image" src="https://github.com/user-attachments/assets/bb149d5e-278d-4747-8165-609eea237d52" />


```sql
SELECT grade, COUNT(*)
FROM customer
WHERE grade>(
    SELECT AVG(grade)   
    FROM customer 
    WHERE city='New York'
)
GROUP BY grade;
```

**Output:**

<img width="564" height="413" alt="image" src="https://github.com/user-attachments/assets/3f916efd-8a65-4be1-a910-a125ac11f3fe" />


**Question 3**
---
<img width="929" height="734" alt="image" src="https://github.com/user-attachments/assets/ee99658f-0260-4d54-9946-6ee3508b8cf1" />


```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

<img width="1276" height="659" alt="image" src="https://github.com/user-attachments/assets/00d43d62-5b9b-48f4-ab45-a034bdb3f777" />


**Question 4**
---
<img width="1237" height="564" alt="image" src="https://github.com/user-attachments/assets/36b7e63c-1be7-473a-82ab-5b28b3336704" />


```sql
SELECT ord_no,purch_amt,ord_date,customer_id,salesman_id
FROM orders
WHERE salesman_id = (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**

<img width="1270" height="491" alt="image" src="https://github.com/user-attachments/assets/7d106315-998c-4473-a1e2-348554d7b1aa" />


**Question 5**
---
<img width="1205" height="619" alt="image" src="https://github.com/user-attachments/assets/0eb42a1d-6485-4708-a783-fe9a1b94a7a1" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);
```

**Output:**

<img width="1278" height="522" alt="image" src="https://github.com/user-attachments/assets/1eaf2a1d-19bf-4412-91ed-f5dedebf66e1" />

**Question 6**
---
<img width="965" height="489" alt="image" src="https://github.com/user-attachments/assets/6e1e004a-3824-49ff-b90b-cfd50195bd41" />


```sql
SELECT * 
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);
```

**Output:**

<img width="878" height="463" alt="image" src="https://github.com/user-attachments/assets/0a987039-469c-47ac-95f5-d2810bd1d00b" />


**Question 7**
---
<img width="1030" height="534" alt="image" src="https://github.com/user-attachments/assets/5a212a0c-a06f-4e21-bae8-d6e51e97a71a" />


```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);
```

**Output:**

<img width="1269" height="567" alt="image" src="https://github.com/user-attachments/assets/be25abcd-9b97-417d-95a0-eac15710eaf5" />


**Question 8**
---
<img width="1040" height="616" alt="image" src="https://github.com/user-attachments/assets/69b7a7c5-5729-4609-a2b0-2f7e023a574c" />


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi' AND AGE < 30
ORDER BY ID ASC;
```

**Output:**

<img width="1267" height="420" alt="image" src="https://github.com/user-attachments/assets/4e5ce2e5-7b5e-4146-9316-d590dda69748" />


**Question 9**
---
<img width="1065" height="559" alt="image" src="https://github.com/user-attachments/assets/1812ef15-c15e-4667-86dc-08ef83cf4511" />


```sql
SELECT name
FROM customer
WHERE phone IN (
  SELECT phone
  FROM customer
  GROUP BY phone
  HAVING COUNT(*) = 1
);
```

**Output:**

<img width="436" height="533" alt="image" src="https://github.com/user-attachments/assets/0bed451b-a5e9-4832-b786-73a6c475e17a" />



**Question 10**
---
<img width="1032" height="674" alt="image" src="https://github.com/user-attachments/assets/8fe4b10e-e5f1-4679-9049-fdced86bab6d" />


```sql
SELECT commission
FROM salesman
WHERE salesman_id IN (
  SELECT salesman_id
  FROM customer
  WHERE city = 'Paris'
);
```

**Output:**

<img width="357" height="403" alt="image" src="https://github.com/user-attachments/assets/679f6eef-5498-4f43-be33-27fc6b23801e" />




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
