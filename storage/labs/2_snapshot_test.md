## <center> HDFS Lab: Test HDFS Snapshots

List the commands and output for each step below in `storage/labs/2_snapshot_test.md`.

* Create a `precious` directory in HDFS; copy the ZIP course file into it.
* Enable snapshots for `precious`
```
hdfs dfs -mkdir precious
hdfs dfs -put /tmp/SEBC-master.zip precious

## CM UI generated command:
hdfs/hdfs.sh ["dfsadmin","-allowSnapshot","/user/isalah89/precious"]
hdfs/hdfs.sh ["dfs","-createSnapshot","/user/isalah89/precious","sebc-hdfs-test"]
```

* Delete the directory

```
[isalah89@n3 ~]$ hdfs dfs -rm -r precious
rm: Failed to move to trash: hdfs://n2.sebcdomain:8020/user/isalah89/precious: The directory /user/isalah89/precious cannot be deleted since /user/isalah89/precious is snapshottable and already has snapshots
```
* Delete the ZIP file
```
[isalah89@n3 ~]$ hdfs dfs -rm  precious/SEBC-master.zip

```

* Restore the deleted file  (via CM)
```
hdfs/hdfs.sh ["dfs","-cp","/user/isalah89/precious/.snapshot/sebc-hdfs-test","/user/isalah89/.snapshot_sebc-hdfs-test_fad42056-65fb-4c96-98e9-14f6dda0f10f"]

[isalah89@n3 ~]$ hdfs dfs -ls precious
Found 1 items
-rw-r--r--   3 hdfs supergroup    1720611 2018-10-16 16:02 precious/SEBC-master.zip

```
