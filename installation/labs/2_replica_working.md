1. Download and implement the official MySQL repo
    * Enable the repo to install MySQL 5.5 on all nodes 
    
    ```
    [imene@n1 ~]$ wget   https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm

    [imene@n1 ~]$ sudo rpm -ivh mysql80-community-release-el6-1.noarch.rpm
    warning: mysql80-community-release-el6-1.noarch.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
    Preparing...                ########################################### [100%]
    1:mysql80-community-relea########################################### [100%]

    [imene@n1 ~]$sudo yum-config-manager --disable mysql80-community
    [imene@n1 ~]$ sudo yum-config-manager --enable mysql55-community
    [imene@n1 ~]$ sudo  yum repolist enabled | grep "mysql*"
   
    ```
    * Install the <code>mysql</code> package on all nodes
     ```
     sudo yum install mysql -y
    ```

    * Install <code>mysql-server</code> on the server and replica nodes (n1,n2)
     ```
     sudo yum install mysql-community-server -y
    ```
    * Download and copy the JDBC connector to all nodes.
    ```
    wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz
    tar zxvf mysql-connector-java-5.1.46.tar.gz
    sudo mkdir -p /usr/share/java/
    cd mysql-connector-java-5.1.46
    sudo cp mysql-connector-java-5.1.46-bin.jar /usr/share/java/mysql-connector-java.jar

    ```
2. You should not need to build a <code>/etc/my.cnf</code> file to start your MySQL server 
* You will have to modify it to support replication. Check MySQL documentation.<p>

```
* n2 server
server_id=2

* n1 server 
log-bin=mysql-bin
server_id=1
```
3. Start the <code>mysqld</code> service.
```
sudo service mysqld start
```
4. Use <code>/usr/bin/mysql_secure_installation</code> to:<br>
    a. Set password protection for the server<br>
    b. Revoke permissions for anonymous users<br>
    c. Permit remote privileged login<br>
    d. Remove test databases<br>
    e. Refresh privileges in memory<br>
    f. Refreshes the <code>mysqld</code> service<p>
5. On the master MySQL node, grant replication privileges for your replica node:<br>
```
[imene@n1 mysql-connector-java-5.1.46]$ mysql -uroot -p
mysql> GRANT REPLICATION SLAVE ON *.* TO slave@172.31.33.154 IDENTIFIED BY 'password';
Query OK, 0 rows affected (0.00 sec)

mysql> SET GLOBAL binlog_format = 'ROW';
Query OK, 0 rows affected (0.00 sec)

mysql> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

```
6. In a second terminal session, log into the MySQL master and show its  status:<br>
    a. <code>mysql> **SHOW MASTER STATUS;**</code><br>
    b. Make note of the file name and byte offset. The replica needs this info to sync to the master.<br>
    c. Logout of the second session; remove the lock on the first with <code>mysql> **UNLOCK TABLES;**</code><p>
```
mysql> SHOW MASTER STATUS;
+------------------+----------+--------------+------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+------------------+----------+--------------+------------------+
| mysql-bin.000003 |     1211 |              |                  |
+------------------+----------+--------------+------------------+
1 row in set (0.00 sec)


** in the first session run :
mysql>  UNLOCK TABLES;
Query OK, 0 rows affected (0.00 sec)

```
7. Login to the replica server and configure a connection to the master:$
```
mysql> CHANGE MASTER TO MASTER_HOST='172.31.33.12', MASTER_USER='slave', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql-bin.000003', MASTER_LOG_POS=1211;
Query OK, 0 rows affected (0.02 sec)

```

8. Initiate slave operations on the replica<br>
```
mysql>  START SLAVE;
Query OK, 0 rows affected (0.00 sec)


mysql> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: 172.31.33.12
                  Master_User: slave
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000003
          Read_Master_Log_Pos: 1211
               Relay_Log_File: mysqld-relay-bin.000003
                Relay_Log_Pos: 253
        Relay_Master_Log_File: mysql-bin.000003
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 1211
              Relay_Log_Space: 556
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
1 row in set (0.00 sec)


```
