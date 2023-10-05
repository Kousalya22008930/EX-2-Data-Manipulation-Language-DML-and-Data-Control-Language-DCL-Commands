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
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/0af1c3bb-025b-43bc-897b-3c21f3b635fd)



### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```sql
delete from manager where salary<2750;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/faac49ed-8998-4624-abd6-9a021194eaef)



### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```sql
select ename as "Name", salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/5ebbf4c9-ed11-4ded-9cfd-96a83ed50c0c)


### Q4)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/e74a5e89-7b60-4d34-981d-d3e08176e56e)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/b772d438-1299-48ab-8531-82a9f14629bb)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/35af3bbc-21a4-4340-afab-1bbbcafc56cc)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/d449b3c2-baed-4e0d-96c4-f3e0316f7993)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename, designation as "job", deptno, hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/cccb2a5d-d06d-4c03-8029-71817e89f4f3)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/ff6b3f10-68d6-475f-bde4-8c49bde1b67e)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/4b0c5ab6-bd78-4cfd-9d52-f4b9792fdb25)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/65b422c9-2b84-436a-a868-1f2a7e9dabd8)

### Q12) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/08813ca4-58a1-438c-a3d6-4976c0be674f)


### Q13) Find maximum, minimum and average salary in EMP table.
MAXIMUM:
### QUERY:
```sql
select max(salary) from manager;
```

### OUTPUT:

![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/f84a7eec-5b64-4cbb-9be7-a9c4c63ec31c)

MINIMUM:
### QUERY:
```sql
select min(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/4d13a404-4fd3-40b5-8d1e-59ac590c40bf)

AVERAGE:
### QUERY:
```sql
select avg(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/618c32ad-6d9d-49f1-ba0e-a65f03387b95)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/Kousalya22008930/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/24b1dffe-991b-4a27-921e-d75b5fe3dfe3)
