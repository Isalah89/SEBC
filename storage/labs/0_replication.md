* Choose a partner in class
* Name a source directory after your GitHub handle
* Name a target directory after your partner's GitHub handle
* Use `teragen` to create a 500 MB file
    ```
    $sudo -u hdfs hdfs dfs -mkdir -p /user/imene/
    $sudo -u hdfs hdfs dfs -chown imene /user/imene
    $hdfs dfs -mkdir /user/imene/Isalah89
    $hdfs dfs -mkdir /user/imene/tizemrane
    $hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen   5000000 /user/imene/Isalah89/teragen-output
    ```

* Copy your partner's file to your target directory 
    * I used `distCp` on the command line

    ```
    hadoop distcp hdfs://ec2-18-194-26-134.eu-central-1.compute.amazonaws.com:8020/user/tarek/tizemrane/* hdfs://n2.sebcdomain:8020/user/imene/tizemrane/

    ```
    It didn't work because I'm using private Ips. so I'll do a copy from&to my cluster
    ```
    hadoop distcp hdfs://n2.sebcdomain:8020/user/imene/Isalah89/teragen-output/* hdfs://n2.sebcdomain:8020/user/imene/tizemrane/
    ```

* Browse the results 
    * Use `hdfs fsck <path> -files -blocks` on your source and target directories
    ```
    [imene@n4 ~]$ hdfs fsck /user/imene/tizemrane -files -blocks
    Connecting to namenode via http://n2.sebcdomain:50070/fsck?ugi=imene&files=1&blocks=1&path=%2Fuser%2Fimene%2Ftizemrane
    FSCK started by imene (auth:SIMPLE) from /172.31.45.194 for path /user/imene/tizemrane at Tue Oct 16 15:30:50 UTC 2018
    /user/imene/tizemrane <dir>
    /user/imene/tizemrane/_SUCCESS 0 bytes, 0 block(s):  OK
    
    /user/imene/tizemrane/part-m-00000 250000000 bytes, 2 block(s): OK
    0.BP-1662568816-172.31.33.154-1539682176757:blk_1073745121_4297 len=134217728 Live_repl=3
    1.BP-1662568816-172.31.33.154-1539682176757:blk_1073745123_4299 len=115782272 Live_repl=3
    
    /user/imene/tizemrane/part-m-00001 250000000 bytes, 2 block(s):  OK
    0. BP-1662568816-172.31.33.154-1539682176757:blk_1073745120_4296 len=134217728 Live_repl=3
    1. BP-1662568816-172.31.33.154-1539682176757:blk_1073745122_4298 len=115782272 Live_repl=3
    
    Status: HEALTHY
    Total size:    500000000 B
    Total dirs:    1
    Total files:   3
    Total symlinks:                0
    Total blocks (validated):      4 (avg. block size 125000000 B)
    Minimally replicated blocks:   4 (100.0 %)
    Over-replicated blocks:        0 (0.0 %)
    Under-replicated blocks:       0 (0.0 %)
    Mis-replicated blocks:         0 (0.0 %)
    Default replication factor:    3
    Average block replication:     3.0
    Corrupt blocks:                0
    Missing replicas:              0 (0.0 %)
    Number of data-nodes:          4
    Number of racks:               1
    FSCK ended at Tue Oct 16 15:30:50 UTC 2018 in 15 milliseconds
    The filesystem under path '/user/imene/tizemrane' is HEALTHY

    ```
    
    ```
    [imene@n4 ~]$ hdfs fsck /user/imene/Isalah89 -files -blocks
    Connecting to namenode via http://n2.sebcdomain:50070/fsck?ugi=imene&files=1&blocks=1&path=%2Fuser%2Fimene%2FIsalah89
    FSCK started by imene (auth:SIMPLE) from /172.31.45.194 for path /user/imene/Isalah89 at Tue Oct 16 15:34:28 UTC 2018
    /user/imene/Isalah89 <dir>
    /user/imene/Isalah89/teragen-output <dir>
    /user/imene/Isalah89/teragen-output/_SUCCESS 0 bytes, 0 block(s):  OK
    
    /user/imene/Isalah89/teragen-output/part-m-00000 250000000 bytes, 2 block(s):  OK
    0. BP-1662568816-172.31.33.154-1539682176757:blk_1073744514_3690 len=134217728 Live_repl=3
    1. BP-1662568816-172.31.33.154-1539682176757:blk_1073744515_3691 len=115782272 Live_repl=3
    
    
    /user/imene/Isalah89/teragen-output/part-m-00001 250000000 bytes, 2 block(s):  OK
    0. BP-1662568816-172.31.33.154-1539682176757:blk_1073744513_3689 len=134217728 Live_repl=3
    1. BP-1662568816-172.31.33.154-1539682176757:blk_1073744516_3692 len=115782272 Live_repl=3
    
    Status: HEALTHY
    Total size:    500000000 B
    Total dirs:    2
    Total files:   3
    Total symlinks:                0
    Total blocks (validated):      4 (avg. block size 125000000 B)
    Minimally replicated blocks:   4 (100.0 %)
    Over-replicated blocks:        0 (0.0 %)
    Under-replicated blocks:       0 (0.0 %)
    Mis-replicated blocks:         0 (0.0 %)
    Default replication factor:    3
    Average block replication:     3.0
    Corrupt blocks:                0
    Missing replicas:              0 (0.0 %)
    Number of data-nodes:          4
    Number of racks:               1
    FSCK ended at Tue Oct 16 15:34:28 UTC 2018 in 1 milliseconds


The filesystem under path '/user/imene/Isalah89' is HEALTHY
    ```