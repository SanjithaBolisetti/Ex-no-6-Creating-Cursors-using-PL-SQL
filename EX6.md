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
create table employee3(empid number,empname varchar(10),dept varchar(10),salary number);
insert into employee3 values(101,'Sadhana','Manager',80000);
insert into employee3 values(102,'Harshitha','HR',85000);
insert into employee3 values(103,'Rithika','IT',70000);
```

### PLSQL Cursor code
```
set serveroutput on
declare
cursor employee3_cursor is
select empid,empname,dept,salary
from employee3;
emp_id number;
emp_name varchar(20);
emp_dept varchar(20);
emp_salary number;
begin
open employee3_cursor;
loop
fetch employee3_cursor into emp_id,emp_name,emp_dept,emp_salary;
exit when employee3_cursor%NOTFOUND;
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
 DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
end loop;
close employee3_cursor;
end;
/
```
### Output:
![image](https://github.com/SanjithaBolisetti/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393633/97e4f248-16e0-41c7-a1bd-f5855dd2e278)


### Result:
THE PROGRAM HAS BEEN IMPLEMENTED SUCCESSFULLY
