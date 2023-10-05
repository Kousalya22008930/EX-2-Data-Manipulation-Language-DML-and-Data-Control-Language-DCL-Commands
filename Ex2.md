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
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/fff837d1-baae-4513-bba2-2c89ae883852)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```sql
delete from manager where salary<=2750;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/a7015e39-f515-45dd-8c40-49be73190e81)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
select ename as "Name", salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/8aa35e7d-433f-41ed-a150-5f9279db0d6b)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```sql
 select ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/3bf03270-3eb5-490b-a29a-4e702d28bf27)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/4d370b3d-506a-43eb-8065-f35647c8748b)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/2129a822-0ffc-4484-999d-ad8dddedcea4)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
 select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:

![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/e9a0a37c-b708-4858-9bb7-92a822df048b)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename, designation as "job", deptno, hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/4f644f3a-9cee-46f3-91c6-a8dfd25d7204)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/3784180f-b089-4144-9756-37c94bc71a77)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/1d5dd4a8-13af-4b44-a256-b6e82fec91fb)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
 select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/0de96161-9bfb-4d58-a5dc-a0a07661c377)


### Q12) Find number of rows in the table EMP

### QUERY:
```sql
 select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/8ed778a7-e5a4-4b34-9ce4-d99f802dc618)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
MAXIMUM:
```sql
select max(salary) from manager;
```

### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/024bceb7-9da8-41f2-9ad4-0bfce3bcc6f4)
MINIMUM:
```sql
select min(salary) from manager;
```
### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/db31cbe2-9c51-4254-8667-753191d60e09)
AVERAGE:
```sql
 select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/bc6d940b-1e78-4307-8a80-9fcf06d290f8)




### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119389108/084168a1-17ea-4a8a-84d8-44f18c16e650)

