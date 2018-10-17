Use CM to answer the following questions. For some questions, search will help you. Watch out for trick questions! (Some of these questions have been asked by customers.

1-  What is ubertask optimization?

When enabled, it allows to run "sufficiently small" jobs sequentially within a single JVM. 
"Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

2-  Where in CM is the Kerberos Security Realm value displayed?
Go to Administration > Settings
-->"default_realm"


3-  Which CDH service(s) host a property for enabling Kerberos authentication?
ZooKeeper

4-  How do you upgrade the CM agents?
after we have upgraded the packages on the Cloudera Manager server host, we have two options :
-  using cloudera manager : 
lunch the upgrade-wizardvia the following URL:
 http://n1.sebcdomain:7180/cmf/upgrade-wizard/welcome

- using the command line on all hosts managed by CM:
    - update cloudera-manager repo /etc/yum.repos.d/cloudera-manager.rep 
    - stop cloudera manager agent 
    - Upgrade the agent packages (yum clean, yum upgrade cloudera-manager-daemons cloudera-manager-agent )
    - start cloudera manager agent

5-  Give the `tsquery` statement used to chart Hue's CPU utilization?

```select cpu_percent where roleType=HUE_SERVER```


6-  Name all the roles that make up the Hive service
- Gateway 
- Hive Metastore Server
- HiveServer2
- WebHCatServer

7-  What steps must be completed before integrating Cloudera Manager with Kerberos?
- Set up a working KDC. Cloudera Manager supports authentication with MIT KDC and Active Directory.
For Hue and Oozie, the Kerberos realm must support renewable tickets.
- Install Kerberos client OS-specific packages on all cluster hosts and client hosts that will authenticate using Kerberos.
- Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC. 

