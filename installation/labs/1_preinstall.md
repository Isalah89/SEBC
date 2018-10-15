### 1. Check vm.swappiness on all your nodes

```
[imene@ip-172-31-33-12 tmp]$ cat /proc/sys/vm/swappiness 
60
[imene@ip-172-31-33-12 tmp]$ sudo sed -i '$a\vm.swappiness=1' /etc/sysctl.conf
[imene@ip-172-31-33-12 tmp]$ tail -5 /etc/sysctl.conf
.
.
kernel.shmmax = 68719476736
#Controls the maximum number of shared memory segments, in pages
kernel.shmall = 4294967296
vm.swappiness=1
[imene@ip-172-31-33-12 tmp]$ sudo sysctl -p
[imene@ip-172-31-33-12 tmp]$ cat /proc/sys/vm/swappiness
1
```

### 2. Show the mount attributes of all volumes

```
[imene@ip-172-31-40-140 root]$ cat /etc/mtab | grep ext4
/dev/xvde1 / ext4 rw 0 0
```
### 3. Show the reserve space of any non-root, ext-based volumes
We have only a root volume.

### 4. Disable transparent hugepage support

Transparent hugepage support is not even enabled in my nodes
```
[imene@ip-172-31-33-12 tmp]$ sudo ls /sys/kernel/mm/transparent_hugepage/defrag
ls: cannot access /sys/kernel/mm/transparent_hugepage/defrag: No such file or directory
[imene@ip-172-31-33-12 tmp]$ sudo ls /sys/kernel/mm/transparent_hugepage/enabled
ls: cannot access /sys/kernel/mm/transparent_hugepage/enabled: No such file or directory
```

### 5. List your network interface configuration
```
[imene@ip-172-31-33-12 tmp]$ ifconfig
eth0      Link encap:Ethernet  HWaddr 06:F0:5F:78:95:E6
          inet addr:172.31.33.12  Bcast:172.31.47.255  Mask:255.255.240.0
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:6419 errors:0 dropped:0 overruns:0 frame:0
          TX packets:4659 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:492292 (480.7 KiB)  TX bytes:510717 (498.7 KiB)
          Interrupt:24

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)

```
### 6. List forward and reverse host lookups using getent or nslookup
```
[root@n3 ~]# for f in  172.31.33.154 n2.sebcdomain 172.31.36.203 n3.sebcdomain 172.31.45.194 n4.sebcdomain 172.31.40.140 n5.sebcdomain 172.31.33.12 n1.sebcdomain ; do getent hosts $f; done
172.31.33.154   n2.sebcdomain
172.31.33.154   n2.sebcdomain
172.31.36.203   n3.sebcdomain
172.31.36.203   n3.sebcdomain
172.31.45.194   n4.sebcdomain
172.31.45.194   n4.sebcdomain
172.31.40.140   n5.sebcdomain
172.31.40.140   n5.sebcdomain
172.31.33.12    n1.sebcdomain
172.31.33.12    n1.sebcdomain

```
### 7. Show the nscd service is running
```
[imene@n1 ~]$ sudo service nscd status
nscd: unrecognized service

[imene@n1 ~]$ sudo yum install nscd

[imene@n1 ~]$ sudo service nscd start
Starting nscd:                                            [  OK  ]
[imene@n1 ~]$ sudo service nscd status
nscd (pid 1103) is running...

```
### 8. Show the ntpd service is running
```

[imene@n1 ~]$ sudo service ntpd status
ntpd: unrecognized service
[imene@n1 ~]$ sudo yum install ntp
[imene@n1 ~]$ sudo service ntpd start
Starting ntpd:                                             [  OK  ]
[imene@n1 ~]$ sudo service ntpd status
ntpd (pid  1229) is running...

```