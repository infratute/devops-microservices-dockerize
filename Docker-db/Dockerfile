# Below line defines the container base image to be used 
FROM mysql:5.7.25
# Set env variable - This usage was found from the MySQL Image documentation from the DockerHub
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"
# Copy the Sql file from the source code into the entrypoint, this given in documentation
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
