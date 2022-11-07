# Multi-stage Dockerfile. Stage 1 is the Build Image, where the artifact will be created.
FROM openjdk:8 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone -b microservices-dockerize-auto-pre-build https://github.com/infratute/devops-microservices-dockerize-compose.git
RUN cd devops-microservices-dockerize-compose/ && mvn install -Dskiptests

# Now lets build the actual Tomcat image

FROM tomcat:8-jre11
RUN rm -rf /usr/local/tomat/webapps/*
# Copy the artifact from the BUILD_IMAGE container image to the new container image's directory.
COPY --from=BUILD_IMAGE devops-microservices-dockerize-compose/target/vprofile-v2.war /usr/local/tomat/webapps/ROOT.war
EXPOSE 80
CMD ["catalina.sh", "run"]
