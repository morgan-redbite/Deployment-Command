# Deployment-Command
#Time is gold

Docker
Image: https://hub.docker.com/

Installation

yum install docker -y
docker --version 


Status/Start/Shutdown

start docker services
service docker start
service docker status

Create container
docker run -d --name tomcat2 -p 8081:8080 {image-name}:latest

Check container
docker ps -a

Log into container
docker exec -it {container-name} /bin/bash


=========================================================================== <br>
Dockerfile
FROM centos:latest
RUN yum install java -y
RUN mkdir /opt/tomcat
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.16/bin/apache-tomcat-10.0.16.tar.gz .
RUN tar -xvzf apache-tomcat-10.0.16.tar.gz
RUN mv apache-tomcat-9.0.54/* /opt/tomcat
EXPOSE 8080
CMD["/opt/tomcat/bin/catalina.sh", "run"]
