FROM bellsoft/liberica-openjdk-alpine-musl:13.0.2-9

MAINTAINER DIABLO Team <DL-Diablo@vli.t-systems.com>

ARG host_proxy=proxy.devops.telekom.de
ARG port_proxy=3128
VOLUME /tmp
ENV http_proxy=http://$host_proxy:$port_proxy \
    https_proxy=http://$host_proxy:$port_proxy \
    HTTP_PROXY=http://$host_proxy:$port_proxy \
   HTTPS_PROXY=http://$host_proxy:$port_proxy

USER 1000

ARG JAR_FILE=build/libs/*.jar

COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","--enable-preview","-jar","/app.jar"]
