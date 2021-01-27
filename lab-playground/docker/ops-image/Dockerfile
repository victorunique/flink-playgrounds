# Compile Job
FROM maven:3.6-jdk-8-slim AS builder
COPY . /opt/lab-ops-playground
WORKDIR /opt/lab-ops-playground
RUN mvn clean install

# Build Image
FROM apache/flink:1.12.1-scala_2.11-java8
WORKDIR /opt/flink/bin
COPY --from=builder /opt/lab-ops-playground/target/flink-playground-clickcountjob-*.jar /opt/ClickCountJob.jar
