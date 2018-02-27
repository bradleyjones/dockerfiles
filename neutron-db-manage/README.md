# neutron-db-manage
Run neutron-db-manage in a container connected to a MariaDB container for
testing the neutron DB locally

Network
=======

Create network to use for containers wanting to connect to mysql db container

`docker network create -d bridge mysql-network`


MySQL Containers
================

MariaDB container connected to mysql-network

`docker run --name neutron-db --net mysql-network -e MYSQL_ROOT_PASSWORD=stackdb -d mariadb`

To execute mysql commands on this db through a mysql shell you can run

`docker run -it --net mysql-network --name mysql-shell mariadb sh -c 'exec mysql -h neutron-db -uroot -pstackdb'`

To run one off mysql commands you can run

`docker run -it --net mysql-network --rm mariadb mysql -h neutron-db -uroot -pstackdb -e "INSERT_MYSQL_COMMAND_HERE"`


neutron-db-manage Container
===========================

`docker run -it --net mysql-network --rm bradleyjones/neutron-db-manage-docker ADD_ANY_NEUTRON-DB-MANAGE_PARAMS_HERE`

If you run this container without any additional params it will run neutron-db-manage current


Create DB before testing
========================

You have to create the neutron DB neutron-db-manage uses to test:

`docker run -it --net mysql-network --rm mariadb mysql -h neutron-db -uroot -pstackdb -e "create database neutron;"`


Aliases
=======

See https://github.com/bradleyjones/dockerfiles/neutron-db-manage/blob/master/aliases
for some useful aliases to add to your environment.
