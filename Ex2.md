# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY: 
UPDATE manager
SET salary = salary + (salary * 0.10);
### OUTPUT:
![Screenshot 2023-09-25 205646](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/b94e1de8-68df-4d0d-8f52-3f39f0645cb9)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
DELETE FROM manager
WHERE salary < 2750;
### OUTPUT:
![Screenshot 2023-09-25 205704](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/2c04f999-e855-42e8-b828-417f24b33c03)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
### OUTPUT:
![Screenshot 2023-09-25 213901](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/5c25ad46-9828-4dc6-a4c1-4c8bbea2add3)

### Q5)	List the names of Clerks from emp table.
### QUERY:
SELECT ename
FROM manager
WHERE designation = 'clerk';
### OUTPUT:
![Screenshot 2023-09-25 210117](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/b3613c7b-44d1-44f4-b6dc-2efc76476f4e)


### Q6)	List the names of employee who are not Managers.
### QUERY:
SELECT ename
FROM manager
WHERE designation <> 'manager';
### OUTPUT:
![Screenshot 2023-09-25 210255](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/b68877e0-1750-4da6-97aa-19e23ae1fec5)


### Q7)	List the names of employees not eligible for commission.
### QUERY:
SELECT ename
FROM manager
WHERE commission = 0;

### OUTPUT:
![Screenshot 2023-09-25 210617](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/45c9fd4d-d554-4f40-89d0-7146ea8b0bc7)


### Q8)	List employees whose name either start or end with ‘s’.
### QUERY:
SELECT ename
FROM manager
WHERE ename LIKE 's%' OR ename LIKE '%s';
### OUTPUT:
![Screenshot 2023-09-25 210902](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/04ce9273-2f11-4c6a-aebc-b63369d45da6)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
SELECT ename, designation AS job, deptno, Hiredate
FROM manager
ORDER BY Hiredate ASC;
### OUTPUT:
![Screenshot 2023-09-25 211026](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/f86198ea-a5aa-436b-bfc6-4663a9e42ad5)


### Q10) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
SELECT *
FROM manager
WHERE Hiredate < '1981-09-30';
### OUTPUT:
![Screenshot 2023-09-25 211209](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/a43b53ac-4c49-434a-b809-1b18302e011b)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
SELECT ename, deptno, salary AS sal
FROM manager
### OUTPUT:
![Screenshot 2023-09-25 211328](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/d44bf9d8-518c-4992-b652-47a3d2fcc777)


### Q12) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
SELECT ename
FROM manager
WHERE deptno NOT IN (30, 40, 10);

### OUTPUT:
![Screenshot 2023-09-25 211439](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/a280f7eb-02bc-4e1f-926a-887706f19aeb)

### Q13) Find number of rows in the table EMP
### QUERY:
SELECT COUNT(*) AS NumberOfRows
FROM manager;
ORDER BY deptno ASC, salary DESC;

### OUTPUT:
![Screenshot 2023-09-25 211546](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/99c9ffc0-2325-432a-8518-51ca514129a2)


### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY:
SELECT MAX(salary) AS MaximumSalary
FROM manager;
SELECT MIN(salary) AS MinimumSalary
FROM manager;
SELECT MIN(salary) AS MinimumSalary
FROM manager;
# MAXIMUM

![Screenshot 2023-09-25 211716](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/cbb91cc8-019d-483c-9165-7bace64616c7)

# MINIMUM
![Screenshot 2023-09-25 211749](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/6303c91f-5c22-4ba6-ba38-aa4e12e9601f)

# AVERAGE

![Screenshot 2023-09-25 213816](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/84096834-1a9b-4d60-af3c-d3dd203f78db)




### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
 SELECT designation AS job, COUNT(*) AS num_employees
FROM manager
GROUP BY designation
ORDER BY num_employees DESC;
### OUTPUT:
![Screenshot 2023-09-25 211942](https://github.com/Vaishnavi-saravanan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118541897/f565d325-6c0c-4dff-9aa0-6792060de1f1)
