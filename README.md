# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands
# AIM:
To create a manager database and execute DML queries using SQL.

# DML(Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data 
Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that 
controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

# List of DML commands:
INSERT: It is used to insert data into a table.
UPDATE: It is used to update existing data within a table.
DELETE: It is used to delete records from a database table.

# Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
# insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
````
# Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
QUERY:
```
UPDATE manager SET salary = salary * 1.10;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/204fc6e6-5e5e-4c87-b8e1-dfc075a0dbba)

# Q2) Delete the records from manager table where the salary less than 2750.
QUERY:
```
DELETE FROM manager WHERE salary < 2750;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/5aabaadf-d352-4c80-9d2e-b5dbbe0d4e44)

# Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
QUERY:
```
SELECT ename AS "Name", (salary * 12) + NVL(commission, 0) AS "Annual Salary" FROM manager;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/68972b69-8aa5-4e0e-8d76-0105fbb5febc)

# Q4) List the names of Clerks from emp table.
QUERY:
```
SELECT ename FROM manager WHERE designation = 'clerk';
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/99dc54fc-f929-4ba3-b6b7-046c30e075b7)

# Q5) List the names of employee who are not Managers.
QUERY:
```
SELECT ename FROM manager WHERE designation != 'manager';
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/26959e21-51f7-4503-983d-ba02436ce576)

# Q6) List the names of employees not eligible for commission.
QUERY:
```
SELECT ename FROM manager WHERE commission = 0;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/4ba5276d-e07b-4266-a843-1dbb8ea25cc9)

# Q7) List employees whose name either start or end with ‘s’.
QUERY:
```
SELECT ename FROM manager WHERE ename LIKE 'S%' OR ename LIKE '%S';
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/d8f7b1cd-9595-4c7a-b0d6-a8cb13a669ba)

# Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
QUERY:
```
SELECT ename, designation, deptno, Hiredate FROM manager ORDER BY hiredate ASC;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/9d1c2b2c-fba0-4900-86e0-efc0a1632b47)

# Q9) List the Details of Employees who have joined before 30 Sept 81.
QUERY:
```
SELECT * FROM manager WHERE Hiredate < TO_DATE('30-SEP-81', 'DD-MON-YY');
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/7eb15c6a-4d1e-4426-b409-171cdc886b01)

# Q10) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
QUERY:
```
SELECT ename, deptno, salary FROM manager ORDER BY deptno ASC, salary DESC;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/a3a5a5ad-19ee-4514-8594-05f4ab770eb5)

# Q11) List the names of employees not belonging to dept no 30,40 & 10
QUERY:
```
SELECT ename FROM manager WHERE deptno NOT IN (10, 30, 40);
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/d18e1d88-bcc6-4249-95c3-c35a98393cf8)

# Q12) Find number of rows in the table EMP
QUERY:
```
SELECT COUNT(*) AS "Number of Rows" FROM manager;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/5fdfbefa-ad22-4b70-b7e6-5cf70c695b3c)

# Q13) Find maximum, minimum and average salary in EMP table.
QUERY:
```
SELECT MAX(salary) AS "Maximum Salary", MIN(salary) AS "Minimum Salary", AVG(salary) AS "Average Salary" FROM manager;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/ed89987a-ac68-4dd1-80f1-8d5340bab785)

# Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
QUERY:
```
SELECT designation, COUNT() AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT() DESC;
```
# OUTPUT:
![image](https://github.com/Thanikasreeb/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119557910/a5d8ea4d-194a-4da1-a81d-673a8f05b8b4)

# RESULT:
Manager database is created and DML queries are executed successsfully.
