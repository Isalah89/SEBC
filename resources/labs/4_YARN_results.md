
Total cluster memory 8G
Total vcores  15

The slowest execution
```
nb mappers = 4
nb reducers = 1
memory = 1024

Teragen:
real    6m16.185s
user    0m14.657s
sys     0m2.478s

*****************************

Terasort:
real    15m4.732s
user    0m18.147s
sys     0m3.028s

```


The fastest  : I used different values of nb mappers for teragen and terasort

```
Teragen
nb mappers = 7
nb reducers = 8
memory = 1024

real    4m58.034s
user    0m13.114s
sys     0m2.211s

*********************************
Terasort
nb mappers = 80
nb reducers = 8
memory = 512

real    12m34.410s
user    0m18.281s
sys     0m2.836s
```


