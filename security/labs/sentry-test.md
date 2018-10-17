Verify user privileges

```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables ;
INFO  : Compiling command(queryId=hive_20181017224141_58aafb18-e80e-46e4-9f70-85f65c34bd24): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017224141_58aafb18-e80e-46e4-9f70-85f65c34bd24); Time taken: 5.704 seconds
INFO  : Executing command(queryId=hive_20181017224141_58aafb18-e80e-46e4-9f70-85f65c34bd24): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017224141_58aafb18-e80e-46e4-9f70-85f65c34bd24); Time taken: 2.145 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (10.184 seconds)
0: jdbc:hive2://localhost:10000/default>
```


Create a Sentry role with full authorization
```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20181017224444_0448da69-d4ac-4c31-a2ec-ef4e258307b0): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017224444_0448da69-d4ac-4c31-a2ec-ef4e258307b0); Time taken: 0.481 seconds
INFO  : Executing command(queryId=hive_20181017224444_0448da69-d4ac-4c31-a2ec-ef4e258307b0): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017224444_0448da69-d4ac-4c31-a2ec-ef4e258307b0); Time taken: 0.274 seconds
INFO  : OK
No rows affected (0.872 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20181017225050_d3cda42a-c005-4a7b-bbc3-04fd8594dc83): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017225050_d3cda42a-c005-4a7b-bbc3-04fd8594dc83); Time taken: 0.731 seconds
INFO  : Executing command(queryId=hive_20181017225050_d3cda42a-c005-4a7b-bbc3-04fd8594dc83): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017225050_d3cda42a-c005-4a7b-bbc3-04fd8594dc83); Time taken: 0.324 seconds
INFO  : OK
No rows affected (1.131 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP isalah89
. . . . . . . . . . . . . . . . . . . .> ;
INFO  : Compiling command(queryId=hive_20181017225050_767a9f01-17fb-48f5-98de-fed747cef0d4): GRANT ROLE sentry_admin TO GROUP isalah89
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017225050_767a9f01-17fb-48f5-98de-fed747cef0d4); Time taken: 0.441 seconds
INFO  : Executing command(queryId=hive_20181017225050_767a9f01-17fb-48f5-98de-fed747cef0d4): GRANT ROLE sentry_admin TO GROUP isalah89
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017225050_767a9f01-17fb-48f5-98de-fed747cef0d4); Time taken: 0.22 seconds
INFO  : OK
No rows affected (0.742 seconds)
0: jdbc:hive2://localhost:10000/default> show tables ;
INFO  : Compiling command(queryId=hive_20181017225151_bac7a786-0638-4d25-8ca3-96e2ab5299b8): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017225151_bac7a786-0638-4d25-8ca3-96e2ab5299b8); Time taken: 0.51 seconds
INFO  : Executing command(queryId=hive_20181017225151_bac7a786-0638-4d25-8ca3-96e2ab5299b8): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017225151_bac7a786-0638-4d25-8ca3-96e2ab5299b8); Time taken: 0.825 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (1.727 seconds)
0: jdbc:hive2://localhost:10000/default>
```


kinit as george, then login to beeline
```
 kinit george@SEBC.COM
Password for george@SEBC.COM:
$ klist
Ticket cache: FILE:/tmp/krb5cc_2005
Default principal: george@SEBC.COM

Valid starting     Expires            Service principal
10/17/18 23:01:14  10/18/18 23:01:14  krbtgt/SEBC.COM@SEBC.COM
        renew until 10/24/18 23:01:14
$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
scan complete in 9ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017230202_cfe8ca86-7e01-4c75-bda5-43e94184f2e1): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017230202_cfe8ca86-7e01-4c75-bda5-43e94184f2e1); Time taken: 0.597 seconds
INFO  : Executing command(queryId=hive_20181017230202_cfe8ca86-7e01-4c75-bda5-43e94184f2e1): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017230202_cfe8ca86-7e01-4c75-bda5-43e94184f2e1); Time taken: 1.049 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (2.029 seconds)
```


kinit as ferdinand , then login to beeline


```
$ kinit ferdinand@SEBC.COM
Password for ferdinand@SEBC.COM:
$beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
scan complete in 11ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/n2.sebcdomain@SEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017230808_2829a6f7-ffa2-4f4c-93d5-c00173281907): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017230808_2829a6f7-ffa2-4f4c-93d5-c00173281907); Time taken: 0.497 seconds
INFO  : Executing command(queryId=hive_20181017230808_2829a6f7-ffa2-4f4c-93d5-c00173281907): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017230808_2829a6f7-ffa2-4f4c-93d5-c00173281907); Time taken: 1.114 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (1.969 seconds)



```
