FROM openjdk:22-ea-15-jdk-slim-bullseye as build

COPY .mvn .mvn
COPY mvnw .
COPY pom.xml .

RUN ./mvnw -B dependency:go-offline                          

COPY src src

RUN ./mvnw -B package                                        

FROM openjdk:22-ea-15-jdk-slim-bullseye

COPY --from=build target/spring-boot-admin-0.0.1-SNAPSHOT.jar .

EXPOSE 9000

ENTRYPOINT ["java", "-jar", "spring-boot-admin-0.0.1-SNAPSHOT.jar"]
