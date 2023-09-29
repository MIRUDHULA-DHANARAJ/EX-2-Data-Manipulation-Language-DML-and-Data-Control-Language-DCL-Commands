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
## OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/8ae6648f-7875-4ccc-a806-347b05003038)



### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/f69371cb-26ed-49a3-876b-76962674972f)


### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete managers where salary<2750;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/08a7557b-0927-4098-81fb-7784a68119c3)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
SELECT
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/48b0ba4d-e63a-46ab-b8ee-b454bd6cc376)

### Q5)	List the names of Clerks from emp table.
### QUERY:
```
select ename from managers where designation='clerk';
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/5d84c889-2d51-4e5d-a629-778efefac930)

### Q6)	List the names of employee who are not Managers.
### QUERY:
```
select ename from managers where designation!='manager';
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/08407513-36cf-488c-a170-ea9d08736e81)

### Q7)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from managers where commission=0;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/d67ab8b4-dcf6-416e-b0ea-cbde6c7538b3)


### Q8)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/a2abb7c0-d6cf-4d08-828a-152f28ac41dc)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```

### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/ee584d1a-db1e-484e-bb71-d05375455b7a)


### Q10) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/b89c5d8b-b30b-415f-af5f-430dec00e7bd)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/1bf997e6-ba50-4866-859f-3f828b83cc1a)

### Q12) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/844202fd-5f6e-476b-b197-f4b779b25e17)


### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managers;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/f9e14c2c-2a13-4904-9f86-4db1d1d777a1)


### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/9ee44ee2-44fb-4031-a7d9-83c340a53e5b)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
### OUTPUT:

![image](https://github.com/MIRUDHULA-DHANARAJ/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94828147/88318f10-dcb3-49f4-b0a9-1f54e5366fda)

## RESULT:
Executing DML queries using SQL was executed successfully.

