#
# Tomcat Dockerfile
#

# Pull base image.
FROM 192.168.199.20:5000/java:8_31
MAINTAINER renpeng.shang<renpeng.shang@woqu.com>

ENV TOMCAT_MAJOR_VERSION 8
ENV TOMCAT_MINOR_VERSION 8.0.20

ADD apache-tomcat-8.0.20 /usr/local/tomcat/

RUN mkdir /tmp/tomcat/

ENV CATALINA_HOME /usr/local/tomcat
ENV CATALINA_BASE /usr/local/tomcat
ENV CATALINA_TMPDIR /tmp/tomcat
ENV CLASSPATH .:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$CATALINA_HOME/bin/bootstrap.jar:$CATALINA_HOME/bin/tomcat-juli.jar

ENV TOMCAT_JVM_ROUTE tomcat80
ENV DEPLOY_DIR ${CATALINA_HOME}/webapps
ENV LIBS_DIR ${CATALINA_HOME}/libs
ENV PATH $PATH:$CATALINA_HOME/bin
ENV JAVA_OPTS="-server -Xms128m -Xmx400m -XX:MaxNewSize=256m"

RUN rm -rf ${CATALINA_HOME}/webapps/* ${CATALINA_HOME}/RELEASE-NOTES ${CATALINA_HOME}/RUNNING.txt ${CATALINA_HOME}/bin/*.bat  ${CATALINA_HOME}/bin/*.tar.gz 

ADD server.xml ${CATALINA_HOME}/conf/server.xml
ADD logging.properties ${CATALINA_HOME}/conf/logging.properties

RUN chmod +x /usr/local/tomcat/bin/*.sh

# Define working directory.
WORKDIR /usr/local/tomcat

CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
