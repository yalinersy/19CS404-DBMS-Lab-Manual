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
---
<img width="1203" height="379" alt="image" src="https://github.com/user-attachments/assets/a8ec2279-98f6-4eed-ab0e-86b6a3d83f7c" />


```
CREATE TABLE Bonuses (
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER REFERENCES Employees(EmployeeID),
    BonusAmount REAL CHECK (BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL
);
```

**Output:**

<img width="1242" height="368" alt="image" src="https://github.com/user-attachments/assets/4f1b17d7-3bc3-4333-ab72-1d2257620c13" />


**Question 2**
---
<img width="939" height="334" alt="image" src="https://github.com/user-attachments/assets/8f4730ef-9def-4e65-8a05-9dda357d69d7" />

```
CREATE TABLE Invoices (
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    DueDate DATE CHECK (DueDate > InvoiceDate),
    Amount REAL CHECK (Amount > 0)
);

```

**Output:**

<img width="1227" height="367" alt="image" src="https://github.com/user-attachments/assets/251a305b-3e2d-436f-8345-55eabb19420b" />


**Question 3**
---
<img width="980" height="290" alt="image" src="https://github.com/user-attachments/assets/993f0b00-16ef-4b78-a728-beed35a9ced8" />


```
ALTER TABLE employee
ADD COLUMN designation varchar(50);

```

**Output:**

<img width="1234" height="375" alt="image" src="https://github.com/user-attachments/assets/f85c26a0-d396-4dc3-9730-d9261ca3ada9" />


**Question 4**
---
<img width="1208" height="295" alt="image" src="https://github.com/user-attachments/assets/d40b9deb-a630-49f4-9274-456e47d78276" />

```
CREATE TABLE Shipments (
    ShipmentID INTEGER PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INTEGER REFERENCES Suppliers(SupplierID),
    OrderID INTEGER REFERENCES Orders(OrderID)
);

```

**Output:**

<img width="1234" height="328" alt="image" src="https://github.com/user-attachments/assets/2cdc1dfc-9eb2-4b51-98a3-234cf6822f4c" />

**Question 5**
---
<img width="1211" height="268" alt="image" src="https://github.com/user-attachments/assets/99302091-eae1-4ed8-9bdf-eb99e2e7ff82" />


```
INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', 2024);

```

**Output:**

<img width="1234" height="326" alt="image" src="https://github.com/user-attachments/assets/cd9b598b-b9f6-46a4-b1f5-bf61a1239a96" />


**Question 6**
---
<img width="1048" height="452" alt="image" src="https://github.com/user-attachments/assets/86abd673-88fa-4f78-9c0e-2d577219419f" />

```
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INTEGER NOT NULL,
    icom_id TEXT CHECK (length(icom_id) = 4),
    FOREIGN KEY (icom_id) REFERENCES company(com_id)
        ON UPDATE CASCADE
        ON DELETE CASCADE
);

```

**Output:**

<img width="1235" height="435" alt="image" src="https://github.com/user-attachments/assets/f48e90f5-fb7b-4d1e-91e9-5b77a641fdc9" />


**Question 7**
---
<img width="1117" height="585" alt="image" src="https://github.com/user-attachments/assets/123cda3b-b8bb-4ef9-8ccc-df94a08dd60d" />


```
ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;

ALTER TABLE Companies
ADD COLUMN dob date;

```

**Output:**

<img width="1236" height="490" alt="image" src="https://github.com/user-attachments/assets/34bb73b8-3bf5-4673-862f-a0bc0f7f97c4" />


**Question 8**
---
<img width="1170" height="467" alt="image" src="https://github.com/user-attachments/assets/05c67b6c-c800-42eb-bffd-463b221daddd" />

```
INSERT INTO Books (ISBN, Title, Author)
VALUES ('978-1234567890', 'Introduction to AI', 'John Doe');

INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-9876543210', 'Deep Learning', 'Jane Doe', 'TechPress', 2022);

INSERT INTO Books (ISBN, Title, Author, Year)
VALUES ('978-1122334455', 'Cybersecurity Essentials', 'Alice Smith', 2021);
```

**Output:**

<img width="1227" height="374" alt="image" src="https://github.com/user-attachments/assets/245b846a-8857-409d-8bda-fab487a2c6f4" />


**Question 9**
---
<img width="909" height="398" alt="image" src="https://github.com/user-attachments/assets/1c9421bf-48f7-41a8-844c-abbdf90a160a" />

```
CREATE TABLE Orders (
    OrderID INTEGER,
    OrderDate TEXT,
    CustomerID INTEGER
);

```

**Output:**

<img width="1231" height="458" alt="image" src="https://github.com/user-attachments/assets/73696189-ca1d-4b7f-8667-d57da47bdbda" />


**Question 10**
---
<img width="730" height="347" alt="image" src="https://github.com/user-attachments/assets/e2548b50-6259-4a2b-a270-f1b0fc5c17ec" />


```
INSERT INTO Employee (EmployeeID, Name, Department, Salary)
SELECT EmployeeID, Name, Department, Salary
FROM Former_employees;
```

**Output:**

<img width="1227" height="353" alt="image" src="https://github.com/user-attachments/assets/74f5c6e7-1ab4-42c8-bd1c-e5d87ff69a22" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
