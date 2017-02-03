# docker-biserver-ce
Pentaho BI server(community edition) 7.0 + MySQL + phpMyAdmin docker image. 

## What's inside
```
ubuntu:16.04
 |
 |-- phusion/baseimage:latest
      |
      |-- zhicwu/java:8
           |
           |-- zhicwu/biserver-ce:7.0
```
* Official Ubuntu 16.04 LTS docker image
* Latest [Phusion Base Image](https://github.com/phusion/baseimage-docker)
* Oracle JDK 8 latest release
* Mysql latest release
* phpMyAdmin latest release
* [Pentaho BI Server Community Edition](http://community.pentaho.com/) 7.0.0.0-25 with plugins and patches:
 * [BTable](https://sourceforge.net/projects/btable/)
 * [Community Text Editor](http://www.webdetails.pt/ctools/cte/)
 * [D3 Component Library](https://github.com/webdetails/d3ComponentLibrary)
 * Up-to-date JDBC drivers: [MySQL Connector/J](http://dev.mysql.com/downloads/connector/j/) 5.1.40, [jTDS](https://sourceforge.net/projects/jtds/) 1.3.1 and [Cassandra JDBC Driver](https://github.com/zhicwu/cassandra-jdbc-driver) 0.6.1
 * [Saiku](http://community.meteorite.bi/) - enabled SaikuWidgetComponent in CDE
 * [XMLA Provider](https://sourceforge.net/projects/xmlaconnect/) 1.0.0.103 - download from Help -> Document popup and install on your windows box

## Known issue
- Not able to import mondrian schema in console, you'll have to use schema workbench to publish schema to BI server

## Get started
- Use docker-compose
```
$ git clone https://github.com/carlosrodriguez85/docker-biserver-ce.git
$ cd docker-biserver-ce
... edit .env and/or docker-compose.yml based on your needs, put your Pentaho configuration files under ext directory if necessary ...
$ docker-compose up -d
$ docker-compose logs -f
```
After the image is started, you should be able to access Pentaho through [http://localhost:8080](http://localhost:8080)(admin/password) or [http://localhost:8080/jamon](http://localhost:8080/jamon)(no login required). Moreover, you will have access to MySQL through phpMyAdmin on [http://localhost:8081](http://localhost:8081)(db/root/password).

## Acknowledgements
Forked from: [https://github.com/zhicwu/docker-biserver-ce]

MySQL + phpMyAdmin configuration from: [http://stackoverflow.com/questions/39054411/docker-connecting-phpmyadmin-to-mysql-doesnt-work]
