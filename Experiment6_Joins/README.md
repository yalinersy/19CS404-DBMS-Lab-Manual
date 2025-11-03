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
--
<img width="1254" height="709" alt="image" src="https://github.com/user-attachments/assets/018e23cf-def6-40b1-a816-cc380cfc87a9" />


```sql
select p.first_name as "patient_name", t.*
from patients p
inner join test_results t
on p.patient_id = t.patient_id
where t.test_name ='Blood Pressure';
```

**Output:**

<img width="1271" height="476" alt="image" src="https://github.com/user-attachments/assets/baed08c5-b424-496b-8550-4b9b434e8218" />


**Question 2**
---
<img width="1231" height="942" alt="image" src="https://github.com/user-attachments/assets/74860804-fb18-4d9b-a28f-ab10e6539a78" />


```sql
select c.cust_name,c.city,c.grade,s.name as Salesman,s.city
from customer c
join salesman s
on c.salesman_id = s.salesman_id
where c.grade<300
order by c.customer_id asc;
```

**Output:**

<img width="1265" height="853" alt="image" src="https://github.com/user-attachments/assets/622f15d4-b9f5-4ab3-9b35-e67daba76b69" />


**Question 3**
---
<img width="1166" height="682" alt="image" src="https://github.com/user-attachments/assets/d45cd673-b42f-4ed3-aa67-39ef708cb590" />


```sql
select p.*
from patients p
inner join test_results t
on p.patient_id=t.patient_id
where test_name='X-Ray' and result='Normal';
```

**Output:**

<img width="1269" height="486" alt="image" src="https://github.com/user-attachments/assets/7eb3eeed-2b06-4e21-bba3-5972ec3227fd" />


**Question 4**
---
<img width="1293" height="960" alt="image" src="https://github.com/user-attachments/assets/2cd99ad3-0e5a-4c52-9ffe-b46e891247d7" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as 'Order Amount'
from customer c
left join orders o
on c.customer_id=o.customer_id  
order by ord_date asc;
```

**Output:**

<img width="1211" height="954" alt="image" src="https://github.com/user-attachments/assets/74a8363c-9392-44b2-9184-1b0e935f0dab" />


**Question 5**
---
<img width="700" height="738" alt="image" src="https://github.com/user-attachments/assets/4d311d82-db31-452a-9edf-f328d587d8ff" />


```sql
select o.ord_no,o.purch_amt,o.ord_date,c.cust_name,c.city as 'customer_city',c.grade,s.name as 'salesman_name',s.city as 'salesman_city',s.commission
from orders o
inner join customer c
on o.customer_id  =c.customer_id  
inner join salesman s
on o.salesman_id=s.salesman_id
```

**Output:**

<img width="1305" height="638" alt="image" src="https://github.com/user-attachments/assets/5ed1095d-9e47-4b23-86b1-feadbab92598" />


**Question 6**
---
<img width="1264" height="429" alt="image" src="https://github.com/user-attachments/assets/7dea7d87-b1b1-45f1-8d46-185aa89b3c66" />


```sql
select c.cust_name,s.name
from customer c
left join salesman s
on c.salesman_id=s.salesman_id
where c.city=s.city;
```

**Output:**

<img width="741" height="609" alt="image" src="https://github.com/user-attachments/assets/3efb0b72-5954-4251-9b26-ee24af6f1161" />

**Question 7**
---
<img width="1278" height="673" alt="image" src="https://github.com/user-attachments/assets/2fe9f3c7-0a80-4156-8261-f8bb279e183c" />


```sql
select p.first_name as 'patient_name'
from patients p
inner join test_results t
on p.patient_id=t.patient_id
where test_name='Blood Pressure';
```

**Output:**

<img width="443" height="464" alt="image" src="https://github.com/user-attachments/assets/f20d3886-638d-4178-9f6c-cf840be48825" />


**Question 8**
---
<img width="1159" height="344" alt="image" src="https://github.com/user-attachments/assets/eea483b4-0d1e-4bde-8041-bd9662ffcfd8" />


```sql
select s.* 
from salesman s 
left join customer c 
on s.salesman_id = c.salesman_id 
where c.cust_name = 'Fabian Johns';
```

**Output:**

<img width="1279" height="472" alt="image" src="https://github.com/user-attachments/assets/417b7570-fbac-44eb-a7ef-ffac5c036c8f" />


**Question 9**
---
<img width="1196" height="875" alt="image" src="https://github.com/user-attachments/assets/878b2c1c-0858-4419-a908-0cf65efc7d79" />


```sql
select c.cust_name as "Customer Name", c.city, s.name as "Salesman", s.commission 
from customer c 
inner join salesman s 
on c.salesman_id = s.salesman_id;

```

**Output:**

<img width="1300" height="880" alt="image" src="https://github.com/user-attachments/assets/4958647e-f833-4ba0-81d0-1e8f52725e85" />


**Question 10**
---
<img width="1161" height="735" alt="image" src="https://github.com/user-attachments/assets/4d41bcb2-4de5-4591-aa22-fea1001a74a3" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as 'Order Amount',s.name,s.commission from customer c
left join orders o on c.customer_id=o.customer_id 
left join salesman s on c.salesman_id=s.salesman_id ;
```

**Output:**

<img width="1063" height="636" alt="image" src="https://github.com/user-attachments/assets/0c768284-40cb-4419-bf4f-85bfa0651e2d" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
