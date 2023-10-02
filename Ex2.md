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
```sql
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![1](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/103926d2-56ce-42a6-879b-c09a73d6138d)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```sql
delete from manager where salary<2750;
```
### OUTPUT:
![2](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/cd39ad9a-e0a5-4ec9-9531-408072998cef)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```sql
select ename as "Name", salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![3](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/f4dd47ca-6cb2-4fa6-aea9-1a0e0f4a09c2)

### Q4)	List the names of Clerks from emp table.
### QUERY:
```sql
select ename from manager where designation='clerk';
```
### OUTPUT:
![4](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/e12a1903-0f12-4ed8-98ba-982a57c106b7)

### Q5)	List the names of employee who are not Managers.
### QUERY:
```sql
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![5](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/c6ef3ace-3ea4-4104-ad66-dfa30c2efe02)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
```sql
select ename from manager where commission=0;
```
### OUTPUT:
![6](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/9bbb0325-a1fb-42b2-9e8c-290a3756f743)

### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![7](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/a85d9e6d-6f51-48f9-852d-0b3fdbebe4dc)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```sql
select ename, designation as "job", deptno, hiredate from manager order by hiredate asc;
```
### OUTPUT:
![8](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/343daa84-2482-4206-af74-f3ff46796904)

### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![9](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/29eb17bb-5f90-41c2-8f67-e9e315e72c3e)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![10](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/9b8a62a0-02f7-4e20-a22c-29ea4f173546)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![11](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/f8260f4a-2a6f-4085-95dd-c3a9a1c55ca2)

### Q12) Find number of rows in the table EMP
### QUERY:
```sql
select count(*) from manager;
```
### OUTPUT:
![12](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/c9d0bef0-c632-47a1-8c00-27eb6e2f9f6f)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
## MAXIMUM:
```sql
select max(salary) from manager;
```
## OUTPUT:
![13_MA](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/74c74eb4-5449-471b-b16a-148a72c51420)

## MINIMUM:
```sql
select min(salary) from manager;
```
## OUTPUT:
![13_MI](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/bbd693d9-362c-4465-9291-5a9b1685b95a)

## AVERAGE:
```sql
select avg(salary) from manager;
```
## OUTPUT:
![13_AV](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/9df0640e-b0ae-4190-b8e6-e4ece264bdb0)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![14](https://github.com/Ronick2005/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/83219341/61ee22fa-a115-455e-8521-447a7ec2a06c)

### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
