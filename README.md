# cloudenabler
The purpose of the CloudEnabler project is aim to help those factory facilities, which don't have the network accessibility, to be accessed by users' smartphone or computer from anywhere.

# cloudenabler-ci-environment
To the quality of RESTful service and make sure the test is close to the real production environment, this project used multiple containers/dockers on a Linux machine to create a continuous integration environment for Mocha testing 

## Prerequisite
 - Install `docker` on your computer. e.g.  `curl -sSL https://get.docker.com | sudo sh` on Linux
 - `git clone` this project
 - Use `ksmt-cloud` command to start the testing environment
 - Use `khub` command to start/stop indvidual nodejs/db/proxy/redis/rabbit-mq server

## Server Architecture

```
API Requests              <->  Node.js 01    <-> Cluster 01  <-> MariaDB 01 + MariaDB 02 + MariaDB 03
 ------>        HAProxy   <->                <-> Cluster 02  <-> MariaDB 04 + MariaDB 05 + MariaDB 06
                          <->  Node.js 02    <-> Cluster 03  <-> MariaDB 07 + MariaDB 08 + MariaDB 09
                                .....             ....           ...
                          <->  Node.js 0x    <-> Cluster 0x  <-> ...
                          <->  Node.js 0x    <-> Cluster 0x  <-> ...
```

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
