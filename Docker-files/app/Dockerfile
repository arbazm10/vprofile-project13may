
#FROM openjdk:11 AS BUILD_IMAGE
#RUN apt update && apt install maven -y
#RUN git clone https://github.com/devopshydclub/vprofile-project.git
#RUN cd vprofile-project && git checkout docker &&  mvn install 


#FROM tomcat:9-jre11
#LABEL "Project"="Vprofile"
#LABEL "Author"="Imran"
#RUN rm -rf /usr/local/tomcat/webapps/*
#COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

#EXPOSE 8080
#CMD ["catalina.sh", "run"]

FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/arbazm10/vprofile-project13may.git
RUN cd vprofile-project13may && git checkout docker && mvn install

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY  --from=BUILD_IMAGE vprofile-project13may/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD [ "catalina.sh", "run" ]
