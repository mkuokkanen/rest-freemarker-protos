# Java web framework prototypes

Simple Java web framework prototypes implementing 
rest endpoints,
json handling and 
html template rendering.

Purpose is to investigate 
how stand alone app is made with given framework 
and what libraries it integrates.

Tested with Java 11.

## Prototyped frameworks

* DropWizard: Jersey JAX-RS + Jetty + Jackson + Freemarker + glue code
* Helidon: 
* Jersey: JAX-RS + Grizzly + Moxy + Freemarker
* Quarkus: JAX-RS 
* RestEasy: JAX-RS + Undertow + Jackson + Freemarker
* Spark: Spark routing + Jetty + GSON + Freemarker
* Spring Boot: 
* Vert.x: Reactive routes + Netty + Jackson + FreeMarker

## Useful maven commands for checking updates

```bash 
mvn versions:display-dependency-updates
mvn versions:display-plugin-updates
```

## Building and running software

### Dropwizard

```bash 
mvn clean install
cd dropwizard
java -jar target/dropwizard-1.0.0-SNAPSHOT.jar server config.yml
```

### Helidon

```bash
mvn clean install
cd helidon
java -jar target/helidon.jar
```

### Jersey

```bash 
mvn clean install
cd jersey/target/
unzip jersey-1.0.0-SNAPSHOT-distribution.zip
java -jar jersey-1.0.0-SNAPSHOT/jersey-1.0.0-SNAPSHOT.jar
```

### Quarkus

```bash 
mvn clean install
cd quarkus
java -jar target/getting-started-1.0-SNAPSHOT-runner.jar
```

### RestEasy

```bash 
mvn clean install
cd resteasy/target/
unzip spark-1.0.0-SNAPSHOT-distribution.zip
java -jar spark-1.0.0-SNAPSHOT/spark-1.0.0-SNAPSHOT.jar
```

### spark

```bash 
mvn clean install
cd spark/target/
unzip resteasy-1.0.0-SNAPSHOT-distribution.zip
java -jar resteasy-1.0.0-SNAPSHOT/resteasy-1.0.0-SNAPSHOT.jar
```


### spring boot

```bash
mvn clean install
cd springboot
java -jar target/springboot-1.0.0-SNAPSHOT.jar
```


### vertx

```bash 
mvn clean install
cd vertx/target/
unzip vertx-1.0.0-SNAPSHOT-distribution.zip
java -jar vertx-1.0.0-SNAPSHOT/vertx-1.0.0-SNAPSHOT.jar 
```

## Testing running software

```bash 
# Request plain text containing "hello world" as string
curl http://localhost:8080/test/hello

# Request HTML page containing "Hello Matti!" from FreeMarker template
curl http://localhost:8080/test/page

# Request JSON object
curl "http://localhost:8080/test/json?name=Mikko&age=20"
```

