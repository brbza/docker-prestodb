# docker-prestodb


This is a docker image for [PrestoDB](https://prestodb.io/) with [Hive connector](https://prestodb.io/docs/current/connector/hive.html).

## Configuration

It requires a working Hive cluster since the default configuration files are for hive connector only. See https://prestodb.io/docs/current/installation/deployment.html Where it assumes Hive metastore listens on `thrift://hive-metastore:9083`

## Start

```SHELL
docker run -d -p 8889:8889 brbza/prestodb:0.214
``` 

## Customize

It's capable to change configuration like `hive.metastore.uri` by binding new directory under `/opt/presto/etc`. E.g., given configuration file `/foo/bar/hive.properties`:

```SHELL
docker run -d -p 8889:8889 -v /foo/bar/hive.properties:/opt/presto/etc/catalog/hive.properties:ro brbza/prestodb:0.214
``` 

