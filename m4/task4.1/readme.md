
# TASK4.1
## Workflow:


<details>
<summary> PART1 </summary>
<br>
Installed MySQL Server. Selected a simple drugstore DB as a model, created database schema via DBDesigner:


![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/DB_schema.png)


Connected to local server through the console, created a database 'drugstore' and filled it with tables and data samples:


![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/DBandTables.png)


Constructed and execute `SELECT` operator with `WHERE`, `GROUP BY` and `ORDER BY` operators, executed other different DDL, DML, DCL queries:


![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Select_Operator.png)


![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Another_statements.png)


Created a new test user and grant him access to `SELECT` operator on 'drugstore' tables; Reconnected as a new user and verified privileges work properly:


![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Users_priviliges.png)


</details>

<details>
<summary>PART2</summary>
<br>
Made a buckup by `mysqldump` utility, droped a table for future restoring:


![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Backup_and_drop_a_table.png)


Restored a database, verified restored table and its' data:


![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Restored_from_dump.png)


Created an AWS RDS database, connected to remote host from console and transfered local DB to remote by dump file. Verified data transfer by executing `SELECT` query from PART1; Created dump to the same file.


![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Transfer_on_RDS_and_Select.png)


Link to 'drugstore' DB dump file: [drugstore_20211130.sql][task4.1-sql]
</details>

<details>
<summary>PART3</summary>
<br>
Created an Amazone DynamoDB table, entered some test data. Queried table with *Scan* and *Query* options:


![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Scan_Query.png)


![Screen10](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/screenshots/Query.png)

</details>




[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>
[task4.1-sql]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/drugsore_20211130.sql>
