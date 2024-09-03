FROM openjdk:21-jdk

COPY ./build/libs/world.jar world.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/world.jar"]