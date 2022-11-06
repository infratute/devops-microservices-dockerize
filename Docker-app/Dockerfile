# Below line defines the container base image to be used 
FROM tomcat:8-jre11
# Below line defines the working directory from where all files will be managed
WORKDIR /usr/local/tomcat/
# Command to be run during the build of the container
RUN rm -rf /usr/local/tomcat/webapps/*
# Copy the files from the local Directory to the container's directory.
COPY vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
# Expose port 8080 of the container
EXPOSE 8080
# Volume of the container that will be used to tag to the host directory for Volume Binding
VOLUME /usr/local/tomcat/webapps/
# Command to be run, before the container is started.
CMD ["catalina.sh", "run"]