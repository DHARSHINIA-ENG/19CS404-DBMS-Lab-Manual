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

**Code:**
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE find_square(num IN NUMBER) IS
    square NUMBER;
BEGIN
    square := num * num;
    DBMS_OUTPUT.PUT_LINE('Square of ' || num || ' is ' || square);
END;
/

BEGIN
    find_square(6);
END;
/
```

**Expected Output:**  
Square of 6 is 36

<img width="312" height="156" alt="image" src="https://github.com/user-attachments/assets/dc5f879d-6bc4-43a1-a0e4-148a1f41b026" />

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Code:**
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE FUNCTION get_factorial(n IN NUMBER)
RETURN NUMBER IS
    fact NUMBER := 1;
    i NUMBER;
BEGIN
    FOR i IN 1..n LOOP
        fact := fact * i;
    END LOOP;
    RETURN fact;
END;
/
DECLARE
    num NUMBER := 5;
    result NUMBER;
BEGIN
    result := get_factorial(num);
    DBMS_OUTPUT.PUT_LINE('Factorial of ' || num || ' is ' || result);
END;
/
```

**Expected Output:**  
Factorial of 5 is 120

<img width="323" height="145" alt="image" src="https://github.com/user-attachments/assets/8ffb31c2-7a3e-4e2e-8b73-2912ce8de1db" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Code:**
```
SET SERVEROUTPUT ON;
CREATE OR REPLACE PROCEDURE check_even_odd(num IN NUMBER) IS
BEGIN
    IF MOD(num, 2) = 0 THEN
        DBMS_OUTPUT.PUT_LINE(num || ' is Even');
    ELSE
        DBMS_OUTPUT.PUT_LINE(num || ' is Odd');
    END IF;
END;
/
BEGIN
    check_even_odd(12);
END;
/
```

**Expected Output:**  
12 is Even

<img width="153" height="150" alt="image" src="https://github.com/user-attachments/assets/7d849535-d5c8-4c88-8dc2-1dde45deeac5" />


---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Code:**
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE FUNCTION reverse_number(num IN NUMBER)
RETURN NUMBER IS
    rev NUMBER := 0;
    rem NUMBER;
    n NUMBER := num;
BEGIN
    WHILE n > 0 LOOP
        rem := MOD(n, 10);    
        rev := (rev * 10) + rem;  
        n := TRUNC(n / 10);         
    END LOOP;
    RETURN rev;
END;
/

DECLARE
    num NUMBER := 1234;
    result NUMBER;
BEGIN
    result := reverse_number(num);
    DBMS_OUTPUT.PUT_LINE('Reversed number of ' || num || ' is ' || result);
END;
/
```

**Expected Output:**  
Reversed number of 1234 is 4321

<img width="368" height="180" alt="image" src="https://github.com/user-attachments/assets/59756d45-b484-4bda-94bd-5246a15ca028" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Code:**
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE print_table(num IN NUMBER) IS
BEGIN
    DBMS_OUTPUT.PUT_LINE('Multiplication table of ' || num || ':');
    
    FOR i IN 1..10 LOOP
        DBMS_OUTPUT.PUT_LINE(num || ' x ' || i || ' = ' || (num * i));
    END LOOP;
END;
/

BEGIN
    print_table(5);
END;
/
```

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

<img width="323" height="363" alt="image" src="https://github.com/user-attachments/assets/b6e8f74e-cbeb-4eaa-8f8c-0d903d2c2afe" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
