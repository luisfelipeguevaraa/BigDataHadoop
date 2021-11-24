# SQOOP

Designed to transfer data between RDBMS and HDFS, usign MapReduce as job to transfer data.
for this example, create a database in Mysql

## Mysql To HDFS and HDF to Mysql

- 1. Use mysql-sql-commands.txt to generate two simple tables

### Import
- 2. Import data from mysql to HDFS => sqoop-commands.txt
     to show data imported
	 
```bash
hadoop fs -cat /user/root/sqoop_import/*
```

### Export
- 3. Export data from HDFS to Mysql => sqoop-commands.txt
     Check in mysql if data loaded

```mysql
select * from sqoop_export;
```