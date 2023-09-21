FROM openjdk:22-ea-14-jdk-slim as build

COPY .mvn .mvn
COPY mvnw .
COPY pom.xml .

RUN ./mvnw -B dependency:go-offline                          

COPY src src

RUN ./mvnw -B package                                        

FROM openjdk:22-ea-14-jdk-slim

COPY --from=build target/customer-self-service-backend-0.0.1-SNAPSHOT.jar .

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "customer-self-service-backend-0.0.1-SNAPSHOT.jar"]
