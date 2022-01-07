# Cloud-native app development on GCP

Use Quarkus to quickly create Cloud-native apps for GCP

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package

# run jar
java -jar target/quarkus-app/quarkus-run.jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar target/*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./mvnw package -Pnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true

# execute your native executable with: 
./target/quarkus-app-1.0.0-SNAPSHOT-runner
```

create a container-image using the native executable
```
./mvnw package -Pnative -Dquarkus.native.container-build=true -Dquarkus.container-image.build=true
```
