FROM maven:3.9.9-eclipse-temurin-21-jammy AS build_image

WORKDIR /vprofile-project
RUN git clone --branch containers https://github.com/hkhcoder/vprofile-project.git .
RUN mvn install -DskipTests
RUN find . -name "*.war"
FROM tomcat:10-jdk21
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build_image /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
