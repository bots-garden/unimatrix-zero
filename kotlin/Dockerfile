# build the application
FROM maven:3.6.0-jdk-8-alpine AS builder
COPY . .
RUN mvn clean package

FROM oracle/graalvm-ce:20.0.0
COPY --from=builder target/*-fat.jar /app.jar
# run the application
CMD [ "java", "-jar", "/app.jar" ]

