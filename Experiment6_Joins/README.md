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

<img width="1264" height="185" alt="image" src="https://github.com/user-attachments/assets/98a25bb1-f18e-47fe-85e5-169917e9c3c8" />


```sql
SELECT DISTINCT c.*
FROM customer c
JOIN orders o
  ON c.customer_id = o.customer_id
WHERE o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

```

**Output:**

<img width="1274" height="590" alt="image" src="https://github.com/user-attachments/assets/4c06d65e-13ab-4218-9a13-e43f00747a24" />


**Question 2**

<img width="1195" height="577" alt="image" src="https://github.com/user-attachments/assets/0d432d3c-86dc-474a-9783-2c3c20a2164f" />


```sql
SELECT 
    p.patient_id,
    p.first_name,
    p.last_name,
    p.date_of_birth,
    p.admission_date,
    p.discharge_date,
    p.doctor_id,
    d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d
    ON p.doctor_id = d.doctor_id;

```

**Output:**


<img width="1277" height="642" alt="image" src="https://github.com/user-attachments/assets/b15459e9-2549-4321-8a42-6892855677b1" />


**Question 3**

<img width="1354" height="137" alt="image" src="https://github.com/user-attachments/assets/26651258-ab6a-4aae-98e3-8b7363d0604e" />


```sql
SELECT s.*
FROM salesman s
LEFT JOIN customer c
  ON s.salesman_id = c.salesman_id
WHERE c.cust_name = 'Fabian Johns';


```

**Output:**

<img width="1272" height="507" alt="image" src="https://github.com/user-attachments/assets/6164dc88-d334-407e-8a4e-1869729dcffc" />


**Question 4**

<img width="1238" height="82" alt="image" src="https://github.com/user-attachments/assets/46fe4f49-c7a0-4e66-a6fe-898bc11de3fd" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c
    ON o.customer_id = c.customer_id
JOIN salesman s
    ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1266" height="520" alt="image" src="https://github.com/user-attachments/assets/398a017e-c678-4bae-9d28-dc218cf0d24e" />


**Question 5**


<img width="1266" height="106" alt="image" src="https://github.com/user-attachments/assets/b5cb70e1-1a43-4638-bf7e-5c1c65ce9beb" />


```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM patients p
INNER JOIN test_results t
    ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';

```

**Output:**


<img width="1280" height="504" alt="image" src="https://github.com/user-attachments/assets/eb511585-3a37-4cab-a061-c2833f357072" />


**Question 6**

<img width="1265" height="82" alt="image" src="https://github.com/user-attachments/assets/eefab1ea-3eed-4e27-89db-539878a8f990" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission
FROM customer c
JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE s.city <> c.city
  AND s.commission > 0.12;

```

**Output:**

<img width="1283" height="709" alt="image" src="https://github.com/user-attachments/assets/d9b8e662-084c-4a9c-b17b-72d917d83f59" />


**Question 7**


<img width="1269" height="71" alt="image" src="https://github.com/user-attachments/assets/4f96b1d4-a49b-4043-b770-7449e82e137c" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;

```

**Output:**

<img width="1249" height="529" alt="image" src="https://github.com/user-attachments/assets/54711c98-d211-4b1d-90a7-9c21d6dec110" />


**Question 8**


<img width="1261" height="74" alt="image" src="https://github.com/user-attachments/assets/4294f46b-a68a-44f7-9ccc-ba24318619b2" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
JOIN customer c
    ON o.customer_id = c.customer_id
JOIN salesman s
    ON o.salesman_id = s.salesman_id;

```

**Output:**


<img width="1271" height="519" alt="image" src="https://github.com/user-attachments/assets/454a8858-7a98-480f-a357-17cf06211583" />


**Question 9**

<img width="1250" height="99" alt="image" src="https://github.com/user-attachments/assets/7b77661a-c403-46c6-958f-a925a6ea670a" />


```sql
SELECT 
    n.nurse_id,
    d.department_name
FROM nurses n
INNER JOIN departments d
    ON n.department_id = d.department_id
WHERE n.first_name = 'David'
  AND n.last_name = 'Moore';

```

**Output:**


<img width="804" height="484" alt="image" src="https://github.com/user-attachments/assets/7a10bffa-26ca-4754-bd37-c5dbb6749e12" />

**Question 10**

<img width="1244" height="70" alt="image" src="https://github.com/user-attachments/assets/39d83d3f-9315-449f-ac29-7e48fc84bfcb" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
JOIN salesman s
    ON c.salesman_id = s.salesman_id;

```

**Output:**


<img width="1281" height="414" alt="image" src="https://github.com/user-attachments/assets/3a39780a-d662-45f3-b299-2fb11a380be1" />

<img width="1526" height="830" alt="image" src="https://github.com/user-attachments/assets/d2ddfd95-f01c-49cd-bc37-541f582566d8" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
