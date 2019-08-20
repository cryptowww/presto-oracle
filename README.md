# Presto OraclePlugin

This is a plugin for Presto that allow you to use Oracle Jdbc Connection

[![Presto-Connectors Member](https://img.shields.io/badge/presto--connectors-member-green.svg)](http://presto-connectors.ml)

## Connection Configuration

Create new properties file inside etc/catalog dir  like ora.properties:

```properties
connector.name=oracle
connection-url=jdbc:oracle:thin:@ip:port:database
connection-user=myuser
connection-password=mypassword
```

​    

## Building Presto Oracle JDBC Plugin

```shell
mvn clean install -DskipTests -Dair.check.skip-all=true
```

then you get a dir presto-oracle-0.223 in target, rename oracle.

and copy the oracle directory to presto-server/plugin

## Building Oracle Driver

Oracle Driver is not available in common repositories, so you will need to download it from Oracle and install manually in your repository.

```shell
mvn install:install-file -DgroupId=com.oracle -DartifactId=ojdbc14 -Dversion=9.0.2.0.0 -Dpackaging=jar -Dfile=ojdbc14.jar
```

