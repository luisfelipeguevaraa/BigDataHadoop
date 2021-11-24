# FLUME

Mecanismo para recolectar, agregar y mover eficientemente grandes cantidades de log streaming data hacia una data centralizado como HDFS, HBase, etc

## Example of steps

Create of file that is use as log, in this case myflume.log 
Copy file configuration of flume to path /root
Create folder in hdfs as myflumetest
sandbox.hortonworks.com => ip from sandbox


```bash
vi /root/myflume.log
hadoop fs -mkdir hdfs://sandbox.hortonworks.com:8020/user/root/myflumetest
```

start flume agent

```bash
flume-ng agent -n agent -c conf -f my_agent.conf
```

start flume agent
```bash
echo "I m testing" >> /root/myflume.log
hadoop fs -cat hdfs://sandbox.hortonworks.com:8020/user/root/myflumetest/*
```

Show files since hdfs, to contrast that automatic is load through flume to hdfs
```bash
hadoop fs -cat hdfs://sandbox.hortonworks.com:8020/user/root/myflumetest/*
```