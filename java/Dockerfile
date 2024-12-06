FROM maven:3-eclipse-temurin-8-alpine as maven

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests
LABEL maintainer="Anthony GOUAT"


FROM eclipse-temurin:8-jre-alpine

COPY --from=maven /app/target/java-0.0.1-SNAPSHOT.jar usr/src/app.jar

EXPOSE 8448
WORKDIR /usr/src

CMD ["java","-jar","app.jar"]

