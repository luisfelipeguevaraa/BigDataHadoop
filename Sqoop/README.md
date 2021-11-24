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

## DISTCP
Tool used for copy distributer this is inter/intra-cluster, for example for a copy from "sqoop_import" to sqoop_import:distcp

```bash
hadoop distcp hdfs://sandbox.hortonworks.com:8020/user/root/sqoop_import hdfs://sandbox.hortonworks.com:8020/user/root/sqoop_import_distcp
```

to check this
```bash
hadoop fs -cat /user/root/sqoop_import_distcp/*
```

other use is simple copy, but distcp will give better performance
```bash
hadoop fs -cp /user/root/sqoop_import /user/root/sqoop_import_cp
hadoop fs -ls /user/root/sqoop_import_cp 
```