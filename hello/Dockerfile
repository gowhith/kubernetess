FROM openjdk:21-jdk

COPY ./build/libs/hello.jar hello.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/hello.jar"]