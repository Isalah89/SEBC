-  DB hostname
```
mysql> select @@hostname
    -> ;
+-----------------+
| @@hostname      |
+-----------------+
| im1.imenedomain |
+-----------------+
1 row in set (0.00 sec)
```

-DB version 
```
mysql> SELECT VERSION()
    -> ;
+------------+
| VERSION()  |
+------------+
| 5.5.61-log |
+------------+
1 row in set (0.00 sec)
```

- Databases 
```
mysql> show databases ;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
```