FROM maven:3.6-jdk-8-alpine as build
ADD ./ app/
WORKDIR /app
RUN mvn install

FROM openjdk:8-jdk-alpine
COPY --from=build /app/target/movie-info-service-0.0.1-SNAPSHOT.jar movie-info-service.jar
EXPOSE 8082
ENTRYPOINT ["java","-jar","movie-info-service.jar"]