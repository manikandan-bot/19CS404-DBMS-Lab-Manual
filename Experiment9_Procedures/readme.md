# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36
## program

<img width="644" height="404" alt="image" src="https://github.com/user-attachments/assets/d61c5e5f-cb6d-4d1c-b8f4-73abee3ef890" />


## output
<img width="339" height="158" alt="image" src="https://github.com/user-attachments/assets/45169ce7-42cf-4bc7-8460-14e8a484fc37" />

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120

## program

<img width="906" height="565" alt="image" src="https://github.com/user-attachments/assets/e8ace861-0ea2-4c24-8056-0ace227b86f4" />

## output

<img width="309" height="163" alt="image" src="https://github.com/user-attachments/assets/2275a26c-2ec5-4534-bca0-5903c4883d4b" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even

## program
<img width="895" height="456" alt="image" src="https://github.com/user-attachments/assets/df19b69d-ed55-4068-a1d4-dea138b6f81a" />

## output
<img width="292" height="132" alt="image" src="https://github.com/user-attachments/assets/657fdc0c-9e91-43b8-b67f-40f2137db06b" />

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321

## program

<img width="849" height="588" alt="image" src="https://github.com/user-attachments/assets/d2cbbe3a-96a1-4fc8-a804-c7a08bfc777f" />

## output

<img width="336" height="123" alt="image" src="https://github.com/user-attachments/assets/13a36817-0f33-40b9-a0fd-d2009b3cf4af" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

## program

<img width="859" height="378" alt="image" src="https://github.com/user-attachments/assets/0fad9bcf-889d-48e4-a4e4-e3c6cd05bc5e" />


## output

<img width="301" height="408" alt="image" src="https://github.com/user-attachments/assets/44f94094-921d-4974-a7d6-44241ed436cb" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
