# how to debug docker

## how to running  (single)

* caddy

```code
docker run -d --name caddy -p 2015:2015 caddy /caddy
```

* strace

> pid && networkspace

```code
docker run -t --pid=container:caddy --net=container:caddy --cap-add sys_admin --cap-add sys_ptrace  dalongrong/alpine-strace
```

## with docker-compose 

* start caddy service

```code
docker-compose up -d caddy
```

* start alpine debug container 

```code
docker-compose up -d alpine
```

* inside alpine container && exec strace (or some utils)

```code
ps -ef 
strace -p <pid>
pmap <pid>
....
```