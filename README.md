# WebPOS

The demo shows a web POS system , which replaces the in-memory product db with online data from 京东.


![](jdpos.png)

To run

```shell
mvn clean spring-boot:run
```

To load testing
```shell
mvn gatling:test
```


Currently, it creates a new session for each user and create a cart for that user session. 
The session data is stored in an in-memory h2 db. It also fetches a product list from jd.com every time a session begins.

1. Build a docker image for this application and run it in docker container with differnet cpus. Perform a load testing against it.
2. Make this system horizontally scalable by using haproxy and perform a load testing against it.
3. Take care of the **cache missing** problem (you may cache the products from jd.com) and **session sharing** problem (you may use a standalone mysql db or a redis cluster). Perform load testings.
4. Change the demo application into **RESTful style and make the server stateless** by saving cart on clients. Perform load testings.

Please **write a report** on the performance differences you notices among the above tasks.

