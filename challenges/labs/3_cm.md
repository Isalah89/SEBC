- hdfs dfs -ls /user

```
[imene@im2 ~]$ sudo -u hdfs hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - fullerton hotels          0 2018-10-19 08:33 /user/fullerton
drwxrwxrwx   - mapred    hadoop          0 2018-10-19 08:31 /user/history
drwxrwxr-t   - hive      hive            0 2018-10-19 08:32 /user/hive
drwxrwxr-x   - hue       hue             0 2018-10-19 08:33 /user/hue
drwxrwxr-x   - oozie     oozie           0 2018-10-19 08:33 /user/oozie
drwxr-xr-x   - raffles   shops           0 2018-10-19 08:33 /user/raffles

```
- CM API call
```
{
  "items" : [ {
    "hostId" : "aa2fa1f1-5275-48bc-bffd-4c46b689dac4",
    "ipAddress" : "172.31.28.11",
    "hostname" : "im1.imenedomain",
    "rackId" : "/default",
    "hostUrl" : "http://im2.imenedomain:7180/cmf/hostRedirect/aa2fa1f1-5275-48bc-bffd-4c46b689dac4",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15428349952
  }, {
    "hostId" : "63e5e574-e8e6-413d-98c8-447c91f3af3e",
    "ipAddress" : "172.31.17.216",
    "hostname" : "im2.imenedomain",
    "rackId" : "/default",
    "hostUrl" : "http://im2.imenedomain:7180/cmf/hostRedirect/63e5e574-e8e6-413d-98c8-447c91f3af3e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15428349952
  }, {
    "hostId" : "a8d08be9-d7cc-4b8f-be21-6f7b4222d245",
    "ipAddress" : "172.31.22.38",
    "hostname" : "im3.imenedomain",
    "rackId" : "/default",
    "hostUrl" : "http://im2.imenedomain:7180/cmf/hostRedirect/a8d08be9-d7cc-4b8f-be21-6f7b4222d245",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15428349952
  }, {
    "hostId" : "488a7fa6-998d-4d76-8941-d6bbf53ea365",
    "ipAddress" : "172.31.22.209",
    "hostname" : "im4.imenedomain",
    "rackId" : "/default",
    "hostUrl" : "http://im2.imenedomain:7180/cmf/hostRedirect/488a7fa6-998d-4d76-8941-d6bbf53ea365",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15428349952
  }, {
    "hostId" : "72c4bc3a-48c5-43fe-b9c8-c7eee526748f",
    "ipAddress" : "172.31.18.26",
    "hostname" : "im5.imenedomain",
    "rackId" : "/default",
    "hostUrl" : "http://im2.imenedomain:7180/cmf/hostRedirect/72c4bc3a-48c5-43fe-b9c8-c7eee526748f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15428349952
  } ]
}
```