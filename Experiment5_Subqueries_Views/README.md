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

<img width="1213" height="521" alt="image" src="https://github.com/user-attachments/assets/800f4253-ef7e-404f-9278-4c8c3b7c4342" />


```sql
SELECT 
    o.ord_no   AS ord_no,
    o.purch_amt,
    o.ord_date AS ord_date,
    o.customer_id,
    o.salesman_id
FROM orders o
JOIN salesman s
    ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

<img width="1246" height="534" alt="image" src="https://github.com/user-attachments/assets/272f88e0-4613-4b39-b434-c664ba2f6527" />


**Question 2**

<img width="1085" height="616" alt="image" src="https://github.com/user-attachments/assets/cc2e4c6f-a0cb-4fea-a01a-426ffc140cfd" />



```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi'
  AND AGE < 30
ORDER BY ID;

```

**Output:**


<img width="1249" height="458" alt="image" src="https://github.com/user-attachments/assets/01387b1e-c0b0-4308-b3b8-165c818e36a7" />


**Question 3**

<img width="1030" height="479" alt="image" src="https://github.com/user-attachments/assets/c29b4156-30a6-43ee-9a1c-ac2042322c36" />


```sql
SELECT *
FROM customer
WHERE customer_id = (
    (SELECT salesman_id
     FROM salesman
     WHERE name = 'Mc Lyon') - 2001
);

```

**Output:**


<img width="1258" height="397" alt="image" src="https://github.com/user-attachments/assets/8fdd07ba-df5c-429c-beb6-a665c08302b8" />


**Question 4**

<img width="1021" height="385" alt="image" src="https://github.com/user-attachments/assets/9b6962ea-74a7-49ff-a3ad-81f14057172f" />


```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;

```

**Output:**


<img width="1228" height="564" alt="image" src="https://github.com/user-attachments/assets/6d8c9d6a-a5c4-4822-8376-a6b474b9d760" />


**Question 5**

<img width="1127" height="455" alt="image" src="https://github.com/user-attachments/assets/247ec882-7244-4cbe-a550-24bf7bf25d53" />



```sql
SELECT department_id, department_name
FROM Departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name))
    FROM Departments
);

```

**Output:**


<img width="636" height="487" alt="image" src="https://github.com/user-attachments/assets/a4bde9b2-4c3f-4932-888f-6461c8fae328" />


**Question 6**

<img width="1063" height="401" alt="image" src="https://github.com/user-attachments/assets/07206bee-7e23-473e-9ea6-0e99afb2e934" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;

```

**Output:**

<img width="1217" height="676" alt="image" src="https://github.com/user-attachments/assets/03b34e57-a263-4eee-ad97-91766343d988" />


**Question 7**

<img width="1215" height="338" alt="image" src="https://github.com/user-attachments/assets/b4d86b0c-4d73-408d-9c1a-28b98d265bdc" />


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


<img width="1269" height="555" alt="image" src="https://github.com/user-attachments/assets/742af8c2-e6de-44e3-a847-ac6a0f32f578" />


**Question 8**

<img width="1253" height="380" alt="image" src="https://github.com/user-attachments/assets/c660251a-dc70-44fd-a44e-5438d9b0c1ff" />

```sql
SELECT *
FROM GRADES g1
WHERE grade = (
    SELECT MIN(grade)
    FROM GRADES g2
    WHERE g2.subject = g1.subject
);

```

**Output:**

<img width="1226" height="532" alt="image" src="https://github.com/user-attachments/assets/a82563fb-93bb-4609-8154-b45e261a8b86" />


**Question 9**

<img width="1034" height="372" alt="image" src="https://github.com/user-attachments/assets/1cba65dd-19e3-4876-9637-7767d90562b2" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**


<img width="1250" height="538" alt="image" src="https://github.com/user-attachments/assets/f4117779-f4b4-4f39-9bf9-150cc1a30aa5" />


**Question 10**


<img width="1014" height="368" alt="image" src="https://github.com/user-attachments/assets/bfc4af2d-8256-4dc8-a96c-405817381d34" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**


<img width="1224" height="412" alt="image" src="https://github.com/user-attachments/assets/672c1c28-7611-4830-a647-ef9cb7e5752c" />

<img width="1519" height="822" alt="image" src="https://github.com/user-attachments/assets/a26cc8c6-649a-44ee-8248-3bdbbf9333c9" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
