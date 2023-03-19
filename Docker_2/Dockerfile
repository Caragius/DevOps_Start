FROM ubuntu:20.04 as builder
COPY boxfuse-sample-java-war-hello /tmp/boxfuse-sample-java-war-hello
WORKDIR /tmp/boxfuse-sample-java-war-hello
RUN apt-get update \
    && apt-get install -y maven \
    && mvn package


FROM tomcat
COPY --from=builder /tmp/boxfuse-sample-java-war-hello/target/*.war /usr/local/tomcat/webapps
EXPOSE 8000
