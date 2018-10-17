
```
## Stop hive
[imene@n1 ~]$ curl -X POST  -u isalah89:cloudera 'http://n1.sebcdomain:7180/api/v12/clusters/Isalah89/services/hive/commands/stop'
{
  "id" : 587,
  "name" : "Stop",
  "startTime" : "2018-10-17T10:27:40.034Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}




## Start hive
[imene@n1 ~]$ curl -X POST  -u isalah89:cloudera 'http://n1.sebcdomain:7180/api/v12/clusters/Isalah89/services/hive/command/start'
{
  "id" : 591,
  "name" : "Start",
  "startTime" : "2018-10-17T10:29:07.863Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}


## Check status
[imene@n1 ~]$ curl  -u isalah89:cloudera 'http://localhost:7180/api/v12/clusters/Isalah89/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://n1.sebcdomain:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://n1.sebcdomain:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}[imene@n1 ~]$
```