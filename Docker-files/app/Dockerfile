FROM openjdk:11 AS build-image
# to build artifact
RUN apt update && apt install maven -y
RUN git clone https://github.com/ajeenkya24/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install


FROM tomcat:9-jre11
LABEL "project"="project1"
LABEL "Author"="Ajeenkya"
#here is the artifact
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build-image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
#here after mvn install vprofile-v2.war file will form , i copied it from target dire to tomcats webapps dir and named it as ROOT.war

EXPOSE 8080
# no need to expose port, when we run image it will auto expose default port 8080
CMD ["catalina.sh", "run"]

