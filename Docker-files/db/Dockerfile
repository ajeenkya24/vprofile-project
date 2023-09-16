FROM mysql:8.0.33
LABEL "project"="project1"
LABEL "Author"="Ajeenkya"

#you have to set var for mysql image thats mandatory
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
# we can any password now bcoz we are override this while running container
# we need to create database by setting variable
ENV MYSQL_DATABASE="accounts"
# now we need move already present db_backup.sql file into image/container
ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql
EXPOSE 3306



