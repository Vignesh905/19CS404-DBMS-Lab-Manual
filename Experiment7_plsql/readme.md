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
#### PL/SQL QUERY:
```SQL
DECLARE
   num1 NUMBER := 80;
   num2 NUMBER := 45;
BEGIN
   IF num1 > num2 THEN
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
   ELSIF num2 > num1 THEN
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
   ELSE
      DBMS_OUTPUT.PUT_LINE('Both numbers are equal: ' || num1);
   END IF;
END;
/
```
### Expected Output: 
Greater number is: 80

### Output Got:
![o1](https://github.com/user-attachments/assets/b5728f2a-5dbe-4034-9fc9-afd70c2638e0)


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
#### PL/SQL QUERY
``` SQL
DECLARE
   n NUMBER := 10;
   i NUMBER := 1;
   sum NUMBER := 0;
BEGIN
   WHILE i <= n LOOP
      sum := sum + i;
      i := i + 1;
   END LOOP;
   
   DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/

```

### Expected Output:
Sum of first 10 natural numbers is: 55

### Output Got:
![o2](https://github.com/user-attachments/assets/dca59c28-5211-49b4-82ab-b9b0044a9239)

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

#### PL/SQL QUERY
``` SQL
DECLARE
   n NUMBER := 7;
   a NUMBER := 0;
   b NUMBER := 1;
   c NUMBER;
   i NUMBER := 3;
   result VARCHAR2(1000);
BEGIN
   result := a || ', ' || b;

   WHILE i <= n LOOP
      c := a + b;
      result := result || ', ' || c;
      a := b;
      b := c;
      i := i + 1;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('n = ' || n);
   DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || result);
END;
/

```
### Expected Output: 
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

### Output Got:
![o3](https://github.com/user-attachments/assets/bb56c659-0143-43f6-9c81-f84c81a6471a)

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

#### PL/SQL QUERY
```SQL
DECLARE
   n NUMBER := 1535;
   original NUMBER := 1535;
   reversed NUMBER := 0;
   digit NUMBER;
BEGIN
   WHILE n > 0 LOOP
      digit := MOD(n, 10);
      reversed := (reversed * 10) + digit;
      n := TRUNC(n / 10);
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('n = ' || original);
   DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;
/

```

### Expected Output:  
n = 1535  
Reversed number is 5351

### Output Got
![o4](https://github.com/user-attachments/assets/7857d294-b0cc-4cf5-8b3c-df505c344352)


## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

#### PL/SQL QUERY
``` SQL
DECLARE
   a NUMBER := 10;
   b NUMBER := 9;
   c NUMBER := 15;
   largest NUMBER;
BEGIN
   IF a >= b AND a >= c THEN
      largest := a;
   ELSIF b >= a AND b >= c THEN
      largest := b;
   ELSE
      largest := c;
   END IF;

   DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
   DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/

```

### Expected Output: 
a = 10, b = 9, c = 15  
Largest of three number is 15
### Output Got:

![o5](https://github.com/user-attachments/assets/d2e4907b-4cf3-4a19-8a80-9a6009d6fe0d)

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
