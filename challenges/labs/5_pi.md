- Run pi 
```
[fullerton@im3 ~]$ kinit fullerton
Password for fullerton@ISALAH89.SG:
[fullerton@im3 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi -Dmapreduce.job.maps=40 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 40 10000
Number of Maps  = 40
Samples per Map = 10000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Wrote input for Map #16
Wrote input for Map #17
Wrote input for Map #18
Wrote input for Map #19
Wrote input for Map #20
Wrote input for Map #21
Wrote input for Map #22
Wrote input for Map #23
Wrote input for Map #24
Wrote input for Map #25
Wrote input for Map #26
Wrote input for Map #27
Wrote input for Map #28
Wrote input for Map #29
Wrote input for Map #30
Wrote input for Map #31
Wrote input for Map #32
Wrote input for Map #33
Wrote input for Map #34
Wrote input for Map #35
Wrote input for Map #36
Wrote input for Map #37
Wrote input for Map #38
Wrote input for Map #39
Starting Job
18/10/19 09:25:05 INFO client.RMProxy: Connecting to ResourceManager at im1.imenedomain/172.31.28.11:8032
18/10/19 09:25:06 INFO hdfs.DFSClient: Created token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539941106083, maxDate=1540545906083, sequenceNumber=3, masterKeyId=2 on 172.31.22.38:8020
18/10/19 09:25:06 INFO security.TokenCache: Got dt for hdfs://im3.imenedomain:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.22.38:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539941106083, maxDate=1540545906083, sequenceNumber=3, masterKeyId=2)
18/10/19 09:25:06 INFO input.FileInputFormat: Total input paths to process : 40
18/10/19 09:25:06 INFO mapreduce.JobSubmitter: number of splits:40
18/10/19 09:25:06 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940554145_0003
18/10/19 09:25:06 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.22.38:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539941106083, maxDate=1540545906083, sequenceNumber=3, masterKeyId=2)
18/10/19 09:25:07 INFO impl.YarnClientImpl: Submitted application application_1539940554145_0003
18/10/19 09:25:07 INFO mapreduce.Job: The url to track the job: http://im1.imenedomain:8088/proxy/application_1539940554145_0003/
18/10/19 09:25:07 INFO mapreduce.Job: Running job: job_1539940554145_0003
18/10/19 09:25:19 INFO mapreduce.Job: Job job_1539940554145_0003 running in uber mode : false
18/10/19 09:25:19 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:25:32 INFO mapreduce.Job:  map 5% reduce 0%
18/10/19 09:25:38 INFO mapreduce.Job:  map 10% reduce 0%
18/10/19 09:25:39 INFO mapreduce.Job:  map 28% reduce 0%
18/10/19 09:25:40 INFO mapreduce.Job:  map 30% reduce 0%
18/10/19 09:25:45 INFO mapreduce.Job:  map 32% reduce 0%
18/10/19 09:25:46 INFO mapreduce.Job:  map 35% reduce 0%
18/10/19 09:25:50 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 09:25:51 INFO mapreduce.Job:  map 55% reduce 0%
18/10/19 09:25:52 INFO mapreduce.Job:  map 57% reduce 0%
18/10/19 09:25:53 INFO mapreduce.Job:  map 60% reduce 0%
18/10/19 09:25:59 INFO mapreduce.Job:  map 63% reduce 0%
18/10/19 09:26:00 INFO mapreduce.Job:  map 65% reduce 0%
18/10/19 09:26:01 INFO mapreduce.Job:  map 68% reduce 0%
18/10/19 09:26:02 INFO mapreduce.Job:  map 85% reduce 0%
18/10/19 09:26:06 INFO mapreduce.Job:  map 88% reduce 0%
18/10/19 09:26:07 INFO mapreduce.Job:  map 90% reduce 0%
18/10/19 09:26:08 INFO mapreduce.Job:  map 93% reduce 0%
18/10/19 09:26:09 INFO mapreduce.Job:  map 95% reduce 0%
18/10/19 09:26:10 INFO mapreduce.Job:  map 98% reduce 0%
18/10/19 09:26:11 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 09:26:12 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:26:12 INFO mapreduce.Job: Job job_1539940554145_0003 completed successfully
18/10/19 09:26:13 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=293
                FILE: Number of bytes written=6191233
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=11030
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=163
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=40
                Launched reduce tasks=1
                Data-local map tasks=40
                Total time spent by all maps in occupied slots (ms)=415543
                Total time spent by all reduces in occupied slots (ms)=7619
                Total time spent by all map tasks (ms)=415543
                Total time spent by all reduce tasks (ms)=7619
                Total vcore-milliseconds taken by all map tasks=415543
                Total vcore-milliseconds taken by all reduce tasks=7619
                Total megabyte-milliseconds taken by all map tasks=425516032
                Total megabyte-milliseconds taken by all reduce tasks=7801856
        Map-Reduce Framework
                Map input records=40
                Map output records=80
                Map output bytes=720
                Map output materialized bytes=1400
                Input split bytes=6310
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=1400
                Reduce input records=80
                Reduce output records=0
                Spilled Records=160
                Shuffled Maps =40
                Failed Shuffles=0
                Merged Map outputs=40
                GC time elapsed (ms)=6537
                CPU time spent (ms)=55380
                Physical memory (bytes) snapshot=18620485632
                Virtual memory (bytes) snapshot=113862172672
                Total committed heap usage (bytes)=19187892224
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=4720
        File Output Format Counters
                Bytes Written=97
Job Finished in 67.24 seconds
Estimated value of Pi is 3.14161000000000000000

real    1m12.654s
user    0m9.870s
sys     0m2.051s



```