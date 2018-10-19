- Run terasort

```
[raffles@im3 ~]$ kinit raffles
Password for raffles@ISALAH89.SG:

[raffles@im3 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapreduce.job.maps=40 -Dmapreduce.job.reduces=10 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819  -Dmapreduce.input.fileinputformat.split.minsize=134217728 -Dmapreduce.input.fileinputformat.split.maxsize=134217728  tgen512 tsort512
18/10/19 09:20:10 INFO terasort.TeraSort: starting
18/10/19 09:20:15 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539940815007, maxDate=1540545615007, sequenceNumber=2, masterKeyId=2 on 172.31.22.38:8020
18/10/19 09:20:15 INFO security.TokenCache: Got dt for hdfs://im3.imenedomain:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.22.38:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539940815007, maxDate=1540545615007, sequenceNumber=2, masterKeyId=2)
18/10/19 09:20:15 INFO input.FileInputFormat: Total input paths to process : 6
Spent 1535ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 1542ms
Sampling 10 splits of 42
Making 10 from 100000 sampled records
Computing parititions took 2258ms
Spent 3803ms computing partitions.
18/10/19 09:20:18 INFO client.RMProxy: Connecting to ResourceManager at im1.imenedomain/172.31.28.11:8032
18/10/19 09:20:19 INFO mapreduce.JobSubmitter: number of splits:42
18/10/19 09:20:19 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940554145_0002
18/10/19 09:20:19 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.22.38:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ISALAH89.SG, renewer=yarn, realUser=, issueDate=1539940815007, maxDate=1540545615007, sequenceNumber=2, masterKeyId=2)
18/10/19 09:20:20 INFO impl.YarnClientImpl: Submitted application application_1539940554145_0002
18/10/19 09:20:20 INFO mapreduce.Job: The url to track the job: http://im1.imenedomain:8088/proxy/application_1539940554145_0002/
18/10/19 09:20:20 INFO mapreduce.Job: Running job: job_1539940554145_0002
18/10/19 09:20:33 INFO mapreduce.Job: Job job_1539940554145_0002 running in uber mode : false
18/10/19 09:20:33 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:20:54 INFO mapreduce.Job:  map 5% reduce 0%
18/10/19 09:20:56 INFO mapreduce.Job:  map 7% reduce 0%
18/10/19 09:20:57 INFO mapreduce.Job:  map 12% reduce 0%
18/10/19 09:21:09 INFO mapreduce.Job:  map 17% reduce 0%
18/10/19 09:21:18 INFO mapreduce.Job:  map 19% reduce 0%
18/10/19 09:21:19 INFO mapreduce.Job:  map 24% reduce 0%
18/10/19 09:21:20 INFO mapreduce.Job:  map 31% reduce 0%
18/10/19 09:21:21 INFO mapreduce.Job:  map 36% reduce 0%
18/10/19 09:21:23 INFO mapreduce.Job:  map 40% reduce 0%
18/10/19 09:21:36 INFO mapreduce.Job:  map 43% reduce 0%
18/10/19 09:21:37 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 09:21:40 INFO mapreduce.Job:  map 50% reduce 0%
18/10/19 09:21:41 INFO mapreduce.Job:  map 60% reduce 0%
18/10/19 09:21:42 INFO mapreduce.Job:  map 62% reduce 0%
18/10/19 09:21:43 INFO mapreduce.Job:  map 64% reduce 0%
18/10/19 09:21:49 INFO mapreduce.Job:  map 67% reduce 0%
18/10/19 09:21:50 INFO mapreduce.Job:  map 69% reduce 0%
18/10/19 09:21:57 INFO mapreduce.Job:  map 71% reduce 0%
18/10/19 09:21:58 INFO mapreduce.Job:  map 74% reduce 0%
18/10/19 09:22:00 INFO mapreduce.Job:  map 79% reduce 0%
18/10/19 09:22:01 INFO mapreduce.Job:  map 83% reduce 0%
18/10/19 09:22:02 INFO mapreduce.Job:  map 86% reduce 0%
18/10/19 09:22:03 INFO mapreduce.Job:  map 88% reduce 0%
18/10/19 09:22:05 INFO mapreduce.Job:  map 90% reduce 0%
18/10/19 09:22:06 INFO mapreduce.Job:  map 93% reduce 0%
18/10/19 09:22:13 INFO mapreduce.Job:  map 98% reduce 0%
18/10/19 09:22:15 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 09:22:21 INFO mapreduce.Job:  map 100% reduce 14%
18/10/19 09:22:26 INFO mapreduce.Job:  map 100% reduce 22%
18/10/19 09:22:27 INFO mapreduce.Job:  map 100% reduce 32%
18/10/19 09:22:29 INFO mapreduce.Job:  map 100% reduce 36%
18/10/19 09:22:32 INFO mapreduce.Job:  map 100% reduce 43%
18/10/19 09:22:33 INFO mapreduce.Job:  map 100% reduce 50%
18/10/19 09:22:35 INFO mapreduce.Job:  map 100% reduce 54%
18/10/19 09:22:36 INFO mapreduce.Job:  map 100% reduce 58%
18/10/19 09:22:37 INFO mapreduce.Job:  map 100% reduce 63%
18/10/19 09:22:38 INFO mapreduce.Job:  map 100% reduce 68%
18/10/19 09:22:39 INFO mapreduce.Job:  map 100% reduce 70%
18/10/19 09:22:42 INFO mapreduce.Job:  map 100% reduce 71%
18/10/19 09:22:43 INFO mapreduce.Job:  map 100% reduce 73%
18/10/19 09:22:44 INFO mapreduce.Job:  map 100% reduce 75%
18/10/19 09:22:45 INFO mapreduce.Job:  map 100% reduce 80%
18/10/19 09:22:46 INFO mapreduce.Job:  map 100% reduce 81%
18/10/19 09:22:48 INFO mapreduce.Job:  map 100% reduce 82%
18/10/19 09:22:50 INFO mapreduce.Job:  map 100% reduce 84%
18/10/19 09:22:51 INFO mapreduce.Job:  map 100% reduce 86%
18/10/19 09:22:52 INFO mapreduce.Job:  map 100% reduce 88%
18/10/19 09:22:54 INFO mapreduce.Job:  map 100% reduce 89%
18/10/19 09:22:56 INFO mapreduce.Job:  map 100% reduce 91%
18/10/19 09:22:57 INFO mapreduce.Job:  map 100% reduce 92%
18/10/19 09:22:58 INFO mapreduce.Job:  map 100% reduce 95%
18/10/19 09:23:02 INFO mapreduce.Job:  map 100% reduce 99%
18/10/19 09:23:04 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:23:06 INFO mapreduce.Job: Job job_1539940554145_0002 completed successfully
18/10/19 09:23:06 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=2289167438
                FILE: Number of bytes written=4551055393
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120005292
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=156
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=20
        Job Counters
                Launched map tasks=42
                Launched reduce tasks=10
                Data-local map tasks=38
                Rack-local map tasks=4
                Total time spent by all maps in occupied slots (ms)=784345
                Total time spent by all reduces in occupied slots (ms)=460244
                Total time spent by all map tasks (ms)=784345
                Total time spent by all reduce tasks (ms)=460244
                Total vcore-milliseconds taken by all map tasks=784345
                Total vcore-milliseconds taken by all reduce tasks=460244
                Total megabyte-milliseconds taken by all map tasks=803169280
                Total megabyte-milliseconds taken by all reduce tasks=471289856
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2253981899
                Input split bytes=5292
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2253981899
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =420
                Failed Shuffles=0
                Merged Map outputs=420
                GC time elapsed (ms)=28377
                CPU time spent (ms)=704230
                Physical memory (bytes) snapshot=30694789120
                Virtual memory (bytes) snapshot=144722100224
                Total committed heap usage (bytes)=30124539904
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5120000000
        File Output Format Counters
                Bytes Written=5120000000
18/10/19 09:23:06 INFO terasort.TeraSort: done

real    2m58.926s
user    0m12.761s
sys     0m2.525s

```