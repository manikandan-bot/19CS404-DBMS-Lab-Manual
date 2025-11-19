# Experiment 10: PL/SQL – Triggers

## AIM
To write and execute PL/SQL trigger programs for automating actions in response to specific table events like INSERT, UPDATE, or DELETE.

---

## THEORY

A **trigger** is a stored PL/SQL block that is automatically executed or fired when a specified event occurs on a table or view. Triggers can be used for enforcing business rules, auditing changes, or automatic updates.

### Types of Triggers:
- **Before Trigger**: Executes before the operation (INSERT, UPDATE, DELETE).
- **After Trigger**: Executes after the operation.
- **Row-level Trigger**: Executes for each affected row.
- **Statement-level Trigger**: Executes once for the triggering statement.

**Basic Syntax:**
```sql
CREATE OR REPLACE TRIGGER trigger_name
BEFORE|AFTER INSERT|UPDATE|DELETE ON table_name
[FOR EACH ROW]
BEGIN
   -- trigger logic
END;
```

## 1. Write a trigger to log every insertion into a table.
**Steps:**
- Create two tables: `employees` (for storing data) and `employee_log` (for logging the inserts).
- Write an **AFTER INSERT** trigger on the `employees` table to log the new data into the `employee_log` table.

**Expected Output:**
- A new entry is added to the `employee_log` table each time a new record is inserted into the `employees` table.

## porgram
<img width="891" height="643" alt="image" src="https://github.com/user-attachments/assets/f4dc7a72-a25d-4d00-ad62-9bd312c2d7da" />


## output
<img width="680" height="437" alt="image" src="https://github.com/user-attachments/assets/cb107c73-fc54-4705-bbc1-cb340d766375" />

---

## 2. Write a trigger to prevent deletion of records from a sensitive table.
**Steps:**
- Write a **BEFORE DELETE** trigger on the `sensitive_data` table.
- Use `RAISE_APPLICATION_ERROR` to prevent deletion and issue a custom error message.

**Expected Output:**
- If an attempt is made to delete a record from `sensitive_data`, an error message is raised, e.g., `ERROR: Deletion not allowed on this table.`

## porgram
<img width="902" height="544" alt="image" src="https://github.com/user-attachments/assets/37403fae-8936-48b3-b42c-b74d9042315a" />


## output
<img width="651" height="390" alt="image" src="https://github.com/user-attachments/assets/f5585eda-ab36-4ae0-9307-ca95e5b93edf" />

---

## 3. Write a trigger to automatically update a `last_modified` timestamp.
**Steps:**
- Add a `last_modified` column to the `products` table.
- Write a **BEFORE UPDATE** trigger on the `products` table to set the `last_modified` column to the current timestamp whenever an update occurs.

**Expected Output:**
- The `last_modified` column in the `products` table is updated automatically to the current date and time when any record is updated.


## porgram
<img width="872" height="596" alt="image" src="https://github.com/user-attachments/assets/501dca9b-efbd-425a-9468-c6f424108b9b" />

## output
<img width="721" height="334" alt="image" src="https://github.com/user-attachments/assets/328aae28-0d33-48c4-96bc-317f8322a0b2" />

---

## 4. Write a trigger to keep track of the number of updates made to a table.
**Steps:**
- Create an `audit_log` table with a counter column.
- Write an **AFTER UPDATE** trigger on the `customer_orders` table to increment the counter in the `audit_log` table every time a record is updated.

**Expected Output:**
- The `audit_log` table will maintain a count of how many updates have been made to the `customer_orders` table.

## porgram

<img width="973" height="670" alt="image" src="https://github.com/user-attachments/assets/d51b7013-b3a9-48d5-8bd6-6afde5717096" />

## output

<img width="460" height="201" alt="image" src="https://github.com/user-attachments/assets/6954f1e8-79f7-4a9e-a154-ee198eb30b7c" />

---

## 5. Write a trigger that checks a condition before allowing insertion into a table.
**Steps:**
- Write a **BEFORE INSERT** trigger on the `employees` table to check if the inserted salary meets a specific condition (e.g., salary must be greater than 3000).
- If the condition is not met, raise an error to prevent the insert.

**Expected Output:**
- If the inserted salary in the `employees` table is below the condition (e.g., salary < 3000), the insert operation is blocked, and an error message is raised, such as: `ERROR: Salary below minimum threshold.`

## porgram

<img width="868" height="561" alt="image" src="https://github.com/user-attachments/assets/7e6dd78c-42a6-4c9d-aac2-18fa988c82b9" />


## output
<img width="689" height="491" alt="image" src="https://github.com/user-attachments/assets/1e250123-04e2-498d-9265-bcd932e44ad5" />


## RESULT
Thus, the PL/SQL trigger programs were written and executed successfully.

