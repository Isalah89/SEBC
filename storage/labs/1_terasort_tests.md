* Create an end-user Linux account named with your GitHub handle
    * Create a home HDFS directory for this user as well
    * Run the following exercises as this user
    ```
  useradd isalah89
  sudo -u hdfs hdfs dfs -mkdir -p /user/isalah89
  sudo -u hdfs hdfs dfs -chown isalah89 /user/isalah89
  su - isalah89
  ```

* Create a 10 GB file using `teragen`
    * Set the number of mappers to four
    * Limit the block size to 32 MB 
    * Land the result under your user's home directory
    * Use the `time` command to report the job's duration
  
    ```
  [isalah89@n3 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -D mapreduce.job.maps=4  -D dfs.blocksize=32M 100000000 /user/isalah89/teragen-output
  
  real    2m18.371s
  user    0m13.361s
  sys     0m2.208s
    
    ```
* Run the `terasort` command on this file 
    * Use the `time` command to report the job's duration
    * Land the result under your user's home directory
    ```
    time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapred.map.tasks.speculative.execution=false /user/isalah89/teragen-output /user/isalah89/terasort_output


    real    18m2.906s
    user    0m19.878s
    sys     0m3.310s

    ```

