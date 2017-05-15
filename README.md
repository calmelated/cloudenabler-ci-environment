# cloudenabler-ci-environment
Using multiple containers/dockers on a Linux machine to create a continuous integration/testing environment 

## Prerequisite
 - Install `docker` on your computer. e.g.  `curl -sSL https://get.docker.com | sudo sh` on Linux
 - `git clone` this project
 - Use `ksmt-cloud` command to start the testing environment
 - Use `khub` to start/stop indvidual nodejs/db/proxy/redis/rabbit-mq sever
 
## Usage

```sh
user@server:~/khub$ ./khub 
Usage:
 ./khub [start|restart|stop] [proxy]
 ./khub [start|restart|stop] [rmq-01  |rmq-02]
 ./khub [start|restart|stop] [redis-01|redis-02    |redis-03]
 ./khub [start|restart|stop] [node-01 |hyec-node-01|yatec-node-01]
 ./khub [start|restart|stop] [node-02 |hyec-node-02|yatec-node-02]
 ./khub [start|restart|stop] [db-01   |hyec-db-01  |yatec-db-01  ]
 ./khub [start|restart|stop] [db-02   |hyec-db-02  |yatec-db-02  ]
 ./khub [start|restart|stop] [db-03   |hyec-db-03  |yatec-db-03  ]
 ./khub [start|restart|stop] [db-04   |hyec-db-04  |yatec-db-04  ]
 ./khub [start|restart|stop] [db-05   |hyec-db-05  |yatec-db-05  ]
 ./khub [start|restart|stop] [db-06   |hyec-db-06  |yatec-db-06  ]
```

```sh
user@server:~/khub$ ./ksmt-cloud 
Usage: 
 ./ksmt-cloud  start
 ./ksmt-cloud  restart
 ./ksmt-cloud  restart-web
 ./ksmt-cloud  stop
```
