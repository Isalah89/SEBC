- Add the first line from your server log

```
[imene@im2 ~]$ sudo head -2  /var/log/cloudera-scm-server/cloudera-scm-server.log
2018-10-19 08:07:10,411 INFO main:com.cloudera.server.cmf.Main: ================================================================================
2018-10-19 08:07:10,441 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.14.4 (#3 built by jenkins on 20180707-0439 git: 0971e84bdceb60db9b96533f46451f40ed8cbdf9)
```

- Add the log line that contains the phrase "Started Jetty server"


```

[imene@im2 ~]$ sudo cat  /var/log/cloudera-scm-server/cloudera-scm-server.log | grep "Started Jetty server"
2018-10-19 08:08:47,899 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.

```

- Copy your db.properties file to challenges/labs/2_db.properties.md


```


[imene@im2 ~]$ sudo cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Oct 19 08:04:37 UTC 2018
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=172.31.28.11:3306
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scmuser
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=password
[imene@im2 ~]$

```