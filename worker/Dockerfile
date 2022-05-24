FROM maven:3.8.4-jdk-11-slim AS builder
WORKDIR /home/popeye
COPY pom.xml .
RUN mvn dependency:resolve
COPY . .
RUN mvn package

FROM openjdk:11-jre-slim
COPY --from=builder "/home/popeye/target/worker-jar-with-dependencies.jar" .
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
