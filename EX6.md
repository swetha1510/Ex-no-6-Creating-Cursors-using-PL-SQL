# Ex. No: 6 Creating Cursors using PL/SQL
### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
create table EMPLOYEE3 (empid NUMBER, empname VARCHAR(20), dept VARCHAR(10),salary NUMBER);
```
### PLSQL Cursor code
```
DECLARE
   CURSOR employee_list_cursor IS
   SELECT empid,empname,dept,salary
   FROM employee_list;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employee_list_cursor;

  LOOP
    FETCH employee_list_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employee_list_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employee_list_cursor;
END;
/
```
### Output:
![Screenshot 2023-10-03 232132](https://github.com/swetha1510/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120623583/890f1659-981c-42d5-bc8c-4f34db3efe87)

### Result:
Thus this program executed successfully.
