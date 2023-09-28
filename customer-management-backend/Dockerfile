FROM openjdk:22-ea-15-jdk-slim-bullseye as build

COPY .mvn .mvn
COPY mvnw .
COPY pom.xml .

RUN ./mvnw -B dependency:go-offline                          

COPY src src

RUN ./mvnw -B package                                        

FROM openjdk:22-ea-15-jdk-slim-bullseye

COPY --from=build target/customer-management-backend-0.0.1-SNAPSHOT.jar .

EXPOSE 8100

ENTRYPOINT ["java", "-jar", "customer-management-backend-0.0.1-SNAPSHOT.jar"]
