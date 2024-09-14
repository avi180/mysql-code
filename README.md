mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| gokul              |
| information_schema |
| mysql              |
| performance_schema |
| sakila             |
| sys                |
| world              |
+--------------------+
mysql> use gokul;
mysql> create table emp1(id int not null, name varchar(20), department varchar(20));
mysql>  insert into emp1(id,name,department)values(12,'kamal','hr');
Query OK, 1 row affected (0.20 sec)

mysql> insert into emp1(id,name,department)values(13,'karan','it'),(14,'ravi','cs');
Query OK, 2 rows affected (0.19 sec)
mysql> select * from emp1;
+----+-------+------------+
| id | name  | department |
+----+-------+------------+
| 12 | kamal | hr         |
| 13 | karan | it         |
| 14 | ravi  | cs         |
+----+-------+------------+
mysql> create table emp2(address varchar(20),regno int(20),phonenumber int(20));
mysql> insert into emp2(address, regno, phonenumber)values('meerut',12,9675),('dehradun',45,890),('ramnagar',13,7569);
mysql> select * from emp2;
+----------+-------+-------------+
| address  | regno | phonenumber |
+----------+-------+-------------+
| meerut   |    12 |        9675 |
| dehradun |    45 |         890 |
| ramnagar |    13 |        7569 |
+----------+-------+-------------+

mysql> select * from emp1 inner join emp2 on emp1.id=emp2.regno;//inner join
 select emp1.name,emp2.address from emp1 inner join emp2 on emp1.id=emp2.regno;// specic colun frominner join
  select * from emp1 left join emp2 on emp1.id=emp2.regno;//left join
   select * from emp1 right join emp2 on emp1.id=emp2.regno;//right join
    select emp2.address,emp2.regno from emp1 right join emp2 on emp1.id=emp2.address order by emp2.address;//order by address 
