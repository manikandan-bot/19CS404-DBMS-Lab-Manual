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

<img width="961" height="305" alt="image" src="https://github.com/user-attachments/assets/52f68854-79bc-4cdf-a2e7-7d56d5e31d29" />


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

<img width="1007" height="758" alt="image" src="https://github.com/user-attachments/assets/3e34478c-f4c3-49fd-a9cc-a14879b5027f" />


**Question 2**

<img width="676" height="321" alt="image" src="https://github.com/user-attachments/assets/52f22ac7-1f7a-4ab2-9d95-e0f987e16b65" />



```sql
SELECT 
    strftime('%H', AppointmentDateTime) AS HourOfDay,
    COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY HourOfDay
ORDER BY HourOfDay;

```

**Output:**

<img width="756" height="615" alt="image" src="https://github.com/user-attachments/assets/c712788a-3062-46c6-b0c1-74f56d2cc15f" />


**Question 3**

---
<img width="876" height="462" alt="image" src="https://github.com/user-attachments/assets/9fce17c4-de12-41a4-bdcc-80bc43c00107" />


```sql
SELECT 
    AVG(income) AS avg_income
FROM employee
WHERE name LIKE 'A%';

```

**Output:**

<img width="502" height="395" alt="image" src="https://github.com/user-attachments/assets/c9f7c41e-a820-4971-bfb3-e274a50acb79" />


**Question 4**

<img width="817" height="462" alt="image" src="https://github.com/user-attachments/assets/b42aeb05-787e-4694-97b1-6c5d885a0173" />



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

<img width="1086" height="401" alt="image" src="https://github.com/user-attachments/assets/2ff36e51-526d-4551-83f4-76a866dc214b" />


**Question 5**

<img width="947" height="285" alt="image" src="https://github.com/user-attachments/assets/5b0467a0-7018-4166-b2a9-24accfafa1ed" />


```sql
SELECT 
    COUNT(*) AS COUNT
FROM customer
WHERE city <> 'Noida';

```

**Output:**


<img width="488" height="395" alt="image" src="https://github.com/user-attachments/assets/94bae382-a51a-458a-a7ea-68f79d1b1990" />


**Question 6**

<img width="1082" height="275" alt="image" src="https://github.com/user-attachments/assets/ed811729-0dff-45e3-8203-19ed9e354192" />


```sql
SELECT SUM(workhour) AS "Total working hours"
FROM employee1;

```

**Output:**

<img width="684" height="397" alt="image" src="https://github.com/user-attachments/assets/5327ae30-32d7-4d1d-a272-cef3d697cd89" />


**Question 7**

<img width="1210" height="294" alt="image" src="https://github.com/user-attachments/assets/6c042ff3-862c-4772-8351-ac569db4ceb6" />


```sql
SELECT 
    age,
    MIN(income) AS "MIN(income)"
FROM employee
GROUP BY age
HAVING MIN(income) < 400000;

```

**Output:**


<img width="712" height="478" alt="image" src="https://github.com/user-attachments/assets/4629bb14-2020-41f5-a46c-5a236f90a393" />


**Question 8**

<img width="1188" height="73" alt="image" src="https://github.com/user-attachments/assets/38984c25-65c3-4aec-bdb2-aad220ab690f" />


```sql
SELECT 
    category_id,
    COUNT(product_name) AS "count(product_name)"
FROM products
GROUP BY category_id
HAVING category_id < 3;

```

**Output:**


<img width="830" height="457" alt="image" src="https://github.com/user-attachments/assets/2fb41939-d691-43ee-bc3f-e6b0d47d737a" />


**Question 9**

<img width="1210" height="190" alt="image" src="https://github.com/user-attachments/assets/7f995c68-b949-4f04-818a-fe93b19796cc" />


```sql
SELECT 
    (age / 5) * 5 AS age_group,
    MAX(salary) AS "MAX(salary)"
FROM customer1
GROUP BY (age / 5) * 5
HAVING MAX(salary) > 8000;

```

**Output:**

<img width="690" height="441" alt="image" src="https://github.com/user-attachments/assets/76735498-49bd-4a4c-be05-abc9978288e5" />


**Question 10**

<img width="1074" height="241" alt="image" src="https://github.com/user-attachments/assets/23b3d59b-e2c3-421d-96d0-2dd98715d67d" />


```sql
select Frequency,count(*) as TotalPrescriptions
from Prescriptions
group by Frequency
```

**Output:**

<img width="868" height="610" alt="image" src="https://github.com/user-attachments/assets/daf17e3e-6f74-4dca-8f4d-a161bb7a470d" />


<img width="1504" height="840" alt="image" src="https://github.com/user-attachments/assets/be4190e3-da5e-4267-aa0a-34ae78c671ba" />




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
