FROM gradle:jdk17-alpine as compile
ADD . /home/source/java
WORKDIR /home/source/java
# Default gradle user is `gradle`. We need to add permission on working directory for gradle to build.
USER root
RUN chown -R gradle /home/source/java
USER gradle
RUN gradle clean build

FROM eclipse-temurin:17-jre
WORKDIR /home/application/java
COPY --from=compile "/home/source/java/build/libs/brinder-profile-api-1.0.0.jar" .
EXPOSE 8080
ENTRYPOINT [ "java", "-jar", "/home/source/java/build/libs/brinder-profile-api-1.0.0.jar"]