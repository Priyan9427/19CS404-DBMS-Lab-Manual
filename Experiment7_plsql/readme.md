# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

##Program:
```
DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 45;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```
##Output:

<img width="342" height="136" alt="Screenshot 2026-05-18 155159" src="https://github.com/user-attachments/assets/82beefd0-64bf-4f11-9684-01f4d4a241ce" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

##Program:
```
DECLARE
    n NUMBER := 10;
    i NUMBER := 1;
    total NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        total := total + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || total);
END;
/
```
##Output:

<img width="362" height="132" alt="Screenshot 2026-05-18 155611" src="https://github.com/user-attachments/assets/a2733776-4ba8-4417-b584-d107ed798421" />


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

##Program:
```
DECLARE
    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER := 3;
BEGIN
    DBMS_OUTPUT.PUT('Fibonacci sequence: ');

    -- Print first two terms
    DBMS_OUTPUT.PUT(a || ', ' || b);

    -- Generate remaining terms
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT(', ' || c);

        a := b;
        b := c;

        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.NEW_LINE;
END;
/
```
##Output:

<img width="367" height="137" alt="Screenshot 2026-05-18 155959" src="https://github.com/user-attachments/assets/7f8e819b-2668-43be-a9e2-756acb4884c0" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

##Program:
```
DECLARE
    n NUMBER := 1535;
    original NUMBER;
    remainder NUMBER;
    reverse_num NUMBER := 0;
BEGIN
    original := n;

    WHILE n > 0 LOOP
        remainder := MOD(n, 10);
        reverse_num := (reverse_num * 10) + remainder;
        n := TRUNC(n / 10);
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reverse_num);
END;
/
```
##Output:

<img width="332" height="126" alt="Screenshot 2026-05-18 160129" src="https://github.com/user-attachments/assets/13361ad7-4f74-4aba-a715-3b4f8089fe3f" />


---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

##Program:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
BEGIN
    IF a > b AND a > c THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || a);

    ELSIF b > a AND b > c THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || b);

    ELSE
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || c);
    END IF;
END;
/
```
##Output:

<img width="370" height="125" alt="Screenshot 2026-05-18 160245" src="https://github.com/user-attachments/assets/4b45c921-b9ad-403f-8bf7-f34b1c617f61" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
