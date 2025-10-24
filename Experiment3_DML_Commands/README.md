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
--
<img width="1126" height="525" alt="image" src="https://github.com/user-attachments/assets/059eb395-1f66-4a59-9a36-c828f4361615" />


```
UPDATE products
SET category = 'Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

<img width="1220" height="565" alt="image" src="https://github.com/user-attachments/assets/03df814b-9a10-430b-a178-5257306d8d38" />


**Question 2**
---
<img width="972" height="207" alt="image" src="https://github.com/user-attachments/assets/56362231-047e-4228-b417-7b5432f3528f" />


```
UPDATE products
SET product_name = 'Grapefruit'
WHERE product_id = 4;
```

**Output:**

<img width="1224" height="294" alt="image" src="https://github.com/user-attachments/assets/d3547e7e-3a7e-4caf-804d-444defb35739" />


**Question 3**
---
<img width="1205" height="578" alt="image" src="https://github.com/user-attachments/assets/085b23e9-3884-4884-9e79-776cb2a4907b" />


```
UPDATE employees
SET salary = 8000
WHERE employee_id = 105
AND salary < 5000;
```

**Output:**

<img width="1233" height="306" alt="image" src="https://github.com/user-attachments/assets/5a3afcbd-47fa-44cc-b9a8-5adbed5b9b20" />


**Question 4**
---
<img width="1225" height="865" alt="image" src="https://github.com/user-attachments/assets/c39272a9-dd52-42ad-a4b4-ecccdd2d21fb" />


```
UPDATE employees
SET salary = CASE
    WHEN department_id = 40  THEN ROUND(salary * 1.25)
    WHEN department_id = 90  THEN ROUND(salary * 1.15)
    WHEN department_id = 110 THEN ROUND(salary * 1.10)
    ELSE salary
END;
```

**Output:**

<img width="1226" height="526" alt="image" src="https://github.com/user-attachments/assets/aa7e2328-7c5c-4d97-818f-b3f90074e35c" />


**Question 5**
---
<img width="1045" height="484" alt="image" src="https://github.com/user-attachments/assets/07a1531e-5456-449e-94b8-b393e6a20cd1" />


```
UPDATE suppliers
SET address = '58 Lakeview, Magnolia'
WHERE supplier_id = 5;
```

**Output:**

<img width="1226" height="464" alt="image" src="https://github.com/user-attachments/assets/bf363648-9b74-4955-818a-350ff27b2335" />


**Question 6**
---
<img width="1219" height="565" alt="image" src="https://github.com/user-attachments/assets/7233474a-eaae-4eb0-8d74-30aeeee444aa" />


```
DELETE FROM Customer
WHERE cust_country NOT IN ('UK', 'USA', 'Canada')
AND grade >= 3;
```

**Output:**

<img width="1219" height="506" alt="image" src="https://github.com/user-attachments/assets/0d7edfaf-d069-4c62-b844-789da20963cc" />


**Question 7**
---
<img width="1220" height="736" alt="image" src="https://github.com/user-attachments/assets/55d0250b-7cbe-4053-8e6f-6a259994f291" />


```
DELETE FROM Customer
WHERE OPENING_AMT BETWEEN 4000 AND 6000;
```

**Output:**

<img width="1215" height="693" alt="image" src="https://github.com/user-attachments/assets/25e851bb-e1ec-40f1-892f-6071b0cc5743" />


**Question 8**
---
<img width="1213" height="491" alt="image" src="https://github.com/user-attachments/assets/702d6f6b-3bdc-484a-8409-a9bc10ec2304" />


```
DELETE FROM customer
WHERE cust_country = 'UK'
AND working_area = 'London'
AND grade < 3;
```

**Output:**

<img width="1224" height="545" alt="image" src="https://github.com/user-attachments/assets/a4e5aa0c-95ef-480b-b1c5-5744d4055e8f" />


**Question 9**
---
<img width="1283" height="842" alt="image" src="https://github.com/user-attachments/assets/f33454ae-82d4-4fac-9107-f87d1bf37362" />


```
DELETE FROM customer
WHERE agent_code IN ('A003', 'A008');
```

**Output:**

<img width="817" height="947" alt="image" src="https://github.com/user-attachments/assets/0522b32a-46e1-4153-96c9-4f0e2bc2c87d" />


**Question 10**
---
<img width="1278" height="495" alt="image" src="https://github.com/user-attachments/assets/abdc583e-f9aa-4324-817c-3be8c27bc56f" />


```
DELETE FROM customer
WHERE working_area = 'New York';
```

**Output:**

<img width="1278" height="698" alt="image" src="https://github.com/user-attachments/assets/9bb5a4ab-dcf8-4521-ad5e-7f96f27ba8e5" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
