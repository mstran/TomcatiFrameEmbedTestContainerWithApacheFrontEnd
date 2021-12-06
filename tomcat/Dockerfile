FROM tomcat:9.0

LABEL maintainer="stranm@microstraninc.com"

COPY server.xml /usr/local/tomcat/conf/

# add context to /usr/local/tomcat/webapps
COPY ./iframetest2.war /usr/local/tomcat/webapps/iframetest2.war

EXPOSE 8009
