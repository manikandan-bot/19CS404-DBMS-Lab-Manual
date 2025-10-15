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
---
<img width="965" height="310" alt="image" src="https://github.com/user-attachments/assets/f17a8c23-1bc4-4b5b-b906-c8a11b5c4b26" />

```sql
SELECT 
    InsuranceCompany,
    AVG(EndDate - StartDate) AS AvgCoverageDurationDays
FROM 
    Insurance
GROUP BY 
    InsuranceCompany;

```

**Output:**

<img width="1046" height="769" alt="image" src="https://github.com/user-attachments/assets/de9fdc73-3c7b-446d-a948-122a959aa8a5" />



**Question 2**

<img width="696" height="632" alt="image" src="https://github.com/user-attachments/assets/abe15fbd-2274-404c-9a45-2893c616b2d2" />




```sql
SELECT 
    strftime('%H', AppointmentDateTime) AS HourOfDay,
    COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY HourOfDay
ORDER BY HourOfDay;
```


**Output:**

<img width="817" height="627" alt="image" src="https://github.com/user-attachments/assets/62712659-32dd-4173-bbdb-def311363843" />


**Question 3**
<img width="951" height="471" alt="image" src="https://github.com/user-attachments/assets/9f3d6df9-3a09-4e8d-8f96-16e77afc1e3b" />



```sql
SELECT 
    AVG(income) AS avg_income
FROM employee
WHERE name LIKE 'A%';
```


**Output:**

<img width="645" height="392" alt="image" src="https://github.com/user-attachments/assets/46299237-0273-4611-be87-a07a51f28b0e" />



**Question 4**

<img width="886" height="480" alt="image" src="https://github.com/user-attachments/assets/90e95931-77a0-4ec0-b042-6d381d219ad8" />


```sql
SELECT 
    name,
    email,
    LENGTH(email) AS min_email_length
FROM customer
ORDER BY LENGTH(email)
LIMIT 1;

```

**Output:**


<img width="1192" height="409" alt="image" src="https://github.com/user-attachments/assets/070a72a8-4e7a-4278-9e55-3793a13b4f8f" />


**Question 5**
<img width="1131" height="507" alt="image" src="https://github.com/user-attachments/assets/4ae63a17-b2db-4c2c-9adc-f1405fcf91ea" />


```sql
SELECT 
    COUNT(*) AS COUNT
FROM customer
WHERE city <> 'Noida';

```

**Output:**

<img width="559" height="407" alt="image" src="https://github.com/user-attachments/assets/8aed1f69-c136-403d-94ef-e85b477f5675" />


**Question 6**

<img width="1093" height="502" alt="image" src="https://github.com/user-attachments/assets/9602959a-60f0-469a-b0ed-56654fe954ba" />


```sql
SELECT SUM(workhour) AS "Total working hours"
FROM employee1;

```

**Output:**


<img width="632" height="390" alt="image" src="https://github.com/user-attachments/assets/3abf07ac-293b-4c6a-94f9-3f3d26dd7980" />


**Question 7**

<img width="1211" height="511" alt="image" src="https://github.com/user-attachments/assets/eb5b1ed9-4efb-408e-ba29-4fdcc22498c2" />


```sql
SELECT 
    age,
    MIN(income) AS "MIN(income)"
FROM employee
GROUP BY age
HAVING MIN(income) < 400000;

```

**Output:**

<img width="754" height="478" alt="image" src="https://github.com/user-attachments/assets/2a79dee6-cd17-4f15-8fc6-b20b1b4e2cae" />


**Question 8**

<img width="1203" height="516" alt="image" src="https://github.com/user-attachments/assets/84dd5f1b-5c17-4f19-a40e-e631f72efdbc" />


```sql
SELECT 
    category_id,
    COUNT(product_name) AS "count(product_name)"
FROM products
GROUP BY category_id
HAVING category_id < 3;

```

**Output:**

<img width="847" height="444" alt="image" src="https://github.com/user-attachments/assets/b3fb7e5e-7d6d-4e73-9259-4aaed4ff4a3e" />


**Question 9**

<img width="1215" height="597" alt="image" src="https://github.com/user-attachments/assets/edcd5c1d-7779-4fb8-bdf5-24854e4fb817" />


```sql
SELECT 
    (age / 5) * 5 AS age_group,
    MAX(salary) AS "MAX(salary)"
FROM customer1
GROUP BY (age / 5) * 5
HAVING MAX(salary) > 8000;

```

**Output:**


<img width="683" height="452" alt="image" src="https://github.com/user-attachments/assets/f90a985f-a11e-4865-8dae-cd26c1f59682" />


**Question 10**


<img width="1025" height="550" alt="image" src="https://github.com/user-attachments/assets/7181f305-26be-43b2-9808-c7c0fbd0f809" />


```sql
select Frequency,count(*) as TotalPrescriptions
from Prescriptions
group by Frequency
```

**Output:**

<img width="911" height="604" alt="image" src="https://github.com/user-attachments/assets/34bba6a9-92e6-407d-892c-11b1b1b62732" />



<img width="1460" height="475" alt="image" src="https://github.com/user-attachments/assets/2fcdc369-68a9-45b2-a6f6-b6a74578fdc4" />



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
