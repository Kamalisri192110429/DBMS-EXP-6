# DBMS-EXP-6mysql> create database travelling;
Query OK, 1 row affected (0.01 sec)

mysql> use travelling;
Database changed
mysql> create table ticket (ticket_ni int(9), journey_date date, age int(4), sex varchar(10),source varchar(10), destination varchar(10), dept_time varchar(10),bus_no int(10));
Query OK, 0 rows affected, 3 warnings (0.03 sec)

mysql> desc ticket;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| ticket_ni    | int         | YES  |     | NULL    |       |
| journey_date | date        | YES  |     | NULL    |       |
| age          | int         | YES  |     | NULL    |       |
| sex          | varchar(10) | YES  |     | NULL    |       |
| source       | varchar(10) | YES  |     | NULL    |       |
| destination  | varchar(10) | YES  |     | NULL    |       |
| dept_time    | varchar(10) | YES  |     | NULL    |       |
| bus_no       | int         | YES  |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
8 rows in set (0.00 sec)

mysql> insert into ticket values(123,"2022-02-10",21,"male","trichy","madurai",7,75),(124,"2022-02-11",50,"female","china","chennai",6,65),(125,"2022-02-12",23,"male","paris","nellore",5,25);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from ticket;
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
| ticket_ni | journey_date | age  | sex    | source | destination | dept_time | bus_no |
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
|       123 | 2022-02-10   |   21 | male   | trichy | madurai     | 7         |     75 |
|       124 | 2022-02-11   |   50 | female | china  | chennai     | 6         |     65 |
|       125 | 2022-02-12   |   23 | male   | paris  | nellore     | 5         |     25 |
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
3 rows in set (0.00 sec)

mysql> select distinct ticket_ni from ticket;
+-----------+
| ticket_ni |
+-----------+
|       123 |
|       124 |
|       125 |
+-----------+
3 rows in set (0.01 sec)

mysql> select * from ticket where sex="male";
+-----------+--------------+------+------+--------+-------------+-----------+--------+
| ticket_ni | journey_date | age  | sex  | source | destination | dept_time | bus_no |
+-----------+--------------+------+------+--------+-------------+-----------+--------+
|       123 | 2022-02-10   |   21 | male | trichy | madurai     | 7         |     75 |
|       125 | 2022-02-12   |   23 | male | paris  | nellore     | 5         |     25 |
+-----------+--------------+------+------+--------+-------------+-----------+--------+
2 rows in set (0.01 sec)

mysql> select source,destination from ticket where dept_time>=5;
+--------+-------------+
| source | destination |
+--------+-------------+
| trichy | madurai     |
| china  | chennai     |
| paris  | nellore     |
+--------+-------------+
3 rows in set (0.01 sec)

mysql> select source,destination from ticket where dept_time>5;
+--------+-------------+
| source | destination |
+--------+-------------+
| trichy | madurai     |
| china  | chennai     |
+--------+-------------+
2 rows in set (0.00 sec)

mysql> select ticket_ni from ticket where destination="chennai";
+-----------+
| ticket_ni |
+-----------+
|       124 |
+-----------+
1 row in set (0.00 sec)

mysql> select * from ticket where age>20 and age<40;
+-----------+--------------+------+------+--------+-------------+-----------+--------+
| ticket_ni | journey_date | age  | sex  | source | destination | dept_time | bus_no |
+-----------+--------------+------+------+--------+-------------+-----------+--------+
|       123 | 2022-02-10   |   21 | male | trichy | madurai     | 7         |     75 |
|       125 | 2022-02-12   |   23 | male | paris  | nellore     | 5         |     25 |
+-----------+--------------+------+------+--------+-------------+-----------+--------+
2 rows in set (0.00 sec)

mysql> select * from ticket where source="paris" or source ="china";
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
| ticket_ni | journey_date | age  | sex    | source | destination | dept_time | bus_no |
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
|       124 | 2022-02-11   |   50 | female | china  | chennai     | 6         |     65 |
|       125 | 2022-02-12   |   23 | male   | paris  | nellore     | 5         |     25 |
+-----------+--------------+------+--------+--------+-------------+-----------+--------+
2 rows in set (0.00 sec)

mysql>
