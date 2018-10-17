
Create keyfile and run kinit, then klist

```
[isalah89@n2 ~]$ ktutil
ktutil:  add_entry -password -p isalah89@SEBC.COM -k 0 -e aes256-cts
Password for isalah89@SEBC.COM:
ktutil:  write_kt isalah89.keytab
ktutil:  quit
[isalah89@n2 ~]$ kdestroy
[isalah89@n2 ~]$ kinit  -k  -t isalah89.keytab isalah89@SEBC.COM
[isalah89@n2 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2005
Default principal: isalah89@SEBC.COM

Valid starting     Expires            Service principal
10/17/18 19:49:54  10/18/18 19:49:54  krbtgt/SEBC.COM@SEBC.COM
        renew until 10/17/18 19:49:54

```