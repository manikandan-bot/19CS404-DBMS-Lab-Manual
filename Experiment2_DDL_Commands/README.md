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
--
-- <img width="1195" height="412" alt="image" src="https://github.com/user-attachments/assets/58811f12-ee5a-4084-807b-20531a6ef32e" />



```sql
ALTER TABLE Student_details ADD COLUMN MobileNumber NUMBER;
ALTER TABLE Student_details ADD COLUMN Address VARCHAR(100);
```

**Output:**
<img width="1208" height="467" alt="image" src="https://github.com/user-attachments/assets/b49c1bdb-3cdc-4852-b8b2-b138c5f94fee" />


**Question 2**
---
<img width="1131" height="238" alt="image" src="https://github.com/user-attachments/assets/ea6c6b30-327f-4fac-84db-fe4a9b324ff2" />


```sql
INSERT INTO Employee (EmployeeID, Name, Position, Department, Salary)
VALUES (001, 'Sarah Parker', 'Manager', 'HR', 60000);

```

**Output:**
<img width="1200" height="320" alt="image" src="https://github.com/user-attachments/assets/aab1e464-3acb-4fcf-8cd6-1c5455e6b721" />


**Question 3**
---
<img width="1092" height="353" alt="image" src="https://github.com/user-attachments/assets/5274e6fe-533e-4719-967d-fdda6137bbd6" />


```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;

```

**Output:**
<img width="1221" height="383" alt="image" src="https://github.com/user-attachments/assets/35af24f3-c97a-4766-b92b-7f500811be4f" />



**Question 4**
---
<img width="881" height="358" alt="image" src="https://github.com/user-attachments/assets/e45dfd71-b748-4a63-95e6-34d8a4c4c75f" />


```sql
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,
    ProductName VARCHAR(100) NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INT CHECK (Stock >= 0)
);

```

**Output:**

<img width="1222" height="361" alt="image" src="https://github.com/user-attachments/assets/2ef57212-4aeb-430e-a341-ab6b16124ad7" />


**Question 5**
---
<img width="1220" height="516" alt="image" src="https://github.com/user-attachments/assets/a6ed7eb7-e56c-41cb-ace4-6838c85f23ab" />



```sql
CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10,2) NOT NULL,
    discount DECIMAL(10,2) NOT NULL DEFAULT 0,
    CHECK (list_price >= discount),
    CHECK (discount >= 0),
    CHECK (list_price >= 0)
);

```

**Output:**

<img width="1223" height="364" alt="image" src="https://github.com/user-attachments/assets/99a00ec7-b92b-4b4e-b28d-c0e6acd681df" />


**Question 6**
---
<img width="1105" height="398" alt="image" src="https://github.com/user-attachments/assets/5313f9de-282b-420e-b5bb-6f14a92993fc" />


```sql
CREATE TABLE Locations (
    LocationID INTEGER,
    LocationName TEXT,
    Address TEXT
);

```

**Output:**

<img width="1231" height="448" alt="image" src="https://github.com/user-attachments/assets/06071a65-6aee-4e48-ae5b-1c7b4bda70f9" />


**Question 7**
---
<img width="814" height="189" alt="image" src="https://github.com/user-attachments/assets/46ea6222-5f12-4dd5-8e18-45633ec32af6" />


```sql
CREATE TABLE Invoices (
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    Amount REAL CHECK (Amount > 0),
    DueDate DATE,
    OrderID INTEGER,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID),
    CHECK (DueDate > InvoiceDate)
);

```

**Output:**
<img width="1223" height="358" alt="image" src="https://github.com/user-attachments/assets/93629979-1a62-453e-8452-fe5c0a7897fd" />


**Question 8**
---
<img width="993" height="297" alt="image" src="https://github.com/user-attachments/assets/e72556bb-7cd1-4096-9fc8-216f17c40229" />


```sql
ALTER TABLE employee
ADD designation varchar(50);

```

**Output:**

<img width="1209" height="367" alt="image" src="https://github.com/user-attachments/assets/7fe3b9ba-7e1a-4d17-909e-114aef374198" />


**Question 9**
---
<img width="1206" height="362" alt="image" src="https://github.com/user-attachments/assets/ae2cb4db-4d34-48bf-81dd-a31fa6322aac" />


```sql
CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);

```

**Output:**

<img width="1217" height="361" alt="image" src="https://github.com/user-attachments/assets/f769714f-3794-4c64-a2fb-2eab41944a0d" />


**Question 10**
---
<img width="1197" height="496" alt="image" src="https://github.com/user-attachments/assets/c419bb25-8bcc-4dfe-9c89-8c43e8a243a8" />


```sql
-- 1. Record with some NULL fields
INSERT INTO Customers (CustomerID, Name, Address) 
VALUES (306, 'Diana Prince', 'Themyscira');

-- 2. Record with all fields filled (no NULL values)
INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode) 
VALUES (307, 'Bruce Wayne', 'Wayne Manor', 'Gotham', '10007');

-- 3. Record with some fields filled and others NULL
INSERT INTO Customers (CustomerID, Name, Address, ZipCode) 
VALUES (308, 'Peter Parker', 'Queens', '11375');

```

**Output:**

<img width="1229" height="373" alt="image" src="https://github.com/user-attachments/assets/e4b21911-4d7a-4e35-a4c3-81bc9d0e499c" />


<img width="1491" height="864" alt="image" src="https://github.com/user-attachments/assets/fc87d7cc-997c-49a0-b934-fb0834183972" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
