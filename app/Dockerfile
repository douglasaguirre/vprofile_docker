# Fase 1 - Build com Maven
FROM maven:3.9.9-eclipse-temurin-21-jammy AS builder

WORKDIR /app

# Aumenta memória heap pro Maven/Java
ENV MAVEN_OPTS="-Xmx1024m"

RUN git clone -b local https://github.com/hkhcoder/vprofile-project.git . \
 && mvn clean package -DskipTests

# Fase 2 - Deploy no Tomcat
FROM tomcat:10-jdk21

RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=builder /app/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

