1. Redis sentinel will modify sentinel.conf, espetially will replace hostname to ip address. For example it will change the following config option from

```
sentinel monitor mymaster redis-1 6379 1
```
to

```
sentinel monitor mymaster 172.31.0.2 6379 1
```
So everytime you tear down the network (e.g docker-compose down) and start again, you need to change ip address back to hostname (i.e redis-1)

2. Redis sentinel will write its id in config file

```
sentinel myid a03f593de4fd4d1a04385642875f21c531accd34
```
so we can't share one sentinel.conf among all sentinel instance

