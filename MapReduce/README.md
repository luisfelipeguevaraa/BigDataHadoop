# Map Reduce


## Example
Write a file with data and after put this in hdfs
ejecute count map reduce with this hdfs folder
finally the response in the amount of word count

```bash
hadoop fs -mkdir mr_word_count_in
hadoop fs -put mr_input_doc.txt mr_word_count_in/
hadoop jar /usr/hdp/2.6.5.0-292/hadoop-mapreduce/hadoop-mapreduce-examples-2.7.3.2.6.5.0-292.jar wordcount /user/root/mr_word_count_in /user/root/mr_word_count_out
hadoop fs -cat /user/root/mr_word_count_out/*
```
