# Config Service

Service which provides config files and properties.

https://cloud.spring.io/spring-cloud-config/

## Requires

Consul
```
  $ docker run \
    -p 8400:8400 \
    -p 8500:8500 \
    -p 8600:53/udp \
    -h node1 \
    progrium/consul -server -bootstrap -ui-dir /ui
```

Rabbit MQ
```
  $ docker run -d \
    --net=host \
    --hostname my-rabbit \
    --name some-rabbit \
    rabbitmq:3
```

## Build

```
  $ mvn clean package
```


## Run

Altering the path for the file locations to where the properties file all reside.

```
  $ java -jar -Dspring.profiles.active=native \
    -Dspring.cloud.config.server.native.searchLocations=file:///home/carl/work/microservices/config-repo \
    target/config-service-1.0-SNAPSHOT.jar
```


