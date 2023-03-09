create table dept
(   
  deptid     number(20),   
  dname      varchar(14)
);
insert into dept(deptid,dname) values(01,'CSE');
insert into dept(deptid,dname) values(02,'ECE');
insert into dept(deptid,dname) values(03,'IT');
insert into dept(deptid,dname) values(04,'CIV');
insert into dept(deptid,dname) values(05,'EEE');

create table emp(   
  empid    number(20),   
  ename    varchar2(10),   
  sal      number(7,2),   
  deptid   number(20)
);
insert into emp(empid,ename,sal,deptid) values(901,'ARUN',70000,'01');
insert into emp(empid,ename,sal,deptid) values(902,'KARTHIK',50000,'01');
insert into emp(empid,ename,sal,deptid) values(903,'KOTESH',60000,'01');
insert into emp(empid,ename,sal,deptid) values(904,'VARUN',30000,'02');
insert into emp(empid,ename,sal,deptid) values(905,'TARUN',30000,'03');
insert into emp(empid,ename,sal,deptid) values(906,'HARUN',60000,'03');
insert into emp(empid,ename,sal,deptid) values(907,'KARUN',50000,'04');
insert into emp(empid,ename,sal,deptid) values(908,'FARUN',70000,'04');
insert into emp(empid,ename,sal,deptid) values(909,'BARUN',20000,'05');
insert into emp(empid,ename,sal,deptid) values(910,'DARUN',25000,'05');

/*ALL*/
select ename from emp where sal = ALL(select sal from emp where sal = 60000);

/*ANY*/
select ename from emp where empid = ANY(select empid from emp where sal =50000);

/*IN*/
select * from dept where dname IN ('CSE','IT','ECE','MECH');

/*NOT IN*/
select * from dept where dname NOT IN ('EEE','CIV','MECH');

/*EXISTS*/
select ename from emp WHERE EXISTS
(SELECT ename FROM emp WHERE sal>50000);

/*NOT EXISTS*/
select ename from emp WHERE NOT EXISTS
(SELECT ename FROM emp WHERE sal>25000);

/*UNION*/
select deptid from dept
UNION
select deptid from emp;

/*UNION ALL*/
select deptid from dept
UNION ALL
select deptid from emp;

/*INTERSECT*/
select deptid from dept
INTERSECT
select deptid from emp;

select * from dept;
select * from emp;

drop table dept;
drop table emp;


---------------------------------------------------------------------------------------------------------------------------------------------------------

create table emp(   
  empid    number(20),   
  ename    varchar2(10),   
  sal      number(7,2),   
  deptid   number(20)
);
insert into emp(empid,ename,sal,deptid) values(901,'ARUN',70000,'01');
insert into emp(empid,ename,sal,deptid) values(902,'KARTHIK',50000,'01');
insert into emp(empid,ename,sal,deptid) values(903,'KOTESH',60000,'01');
insert into emp(empid,ename,sal,deptid) values(904,'VARUN',30000,'02');
insert into emp(empid,ename,sal,deptid) values(905,'TARUN',30000,'03');
insert into emp(empid,ename,sal,deptid) values(906,'HARUN',60000,'03');
insert into emp(empid,ename,sal,deptid) values(907,'KARUN',50000,'04');
insert into emp(empid,ename,sal,deptid) values(908,'FARUN',70000,'04');
insert into emp(empid,ename,sal,deptid) values(909,'BARUN',20000,'05');
insert into emp(empid,ename,sal,deptid) values(910,'DARUN',25000,'05');

select max(sal) from emp;
select min(sal) from emp;
select count(sal) from emp;
select avg(sal) from emp;
select sum(sal) from emp;




---------------------------------------------------------------------------------------------------------------------------------------------------------
