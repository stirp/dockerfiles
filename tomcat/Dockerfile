Dockerfile
[root@10-10-40-117 tomcat]# cat Dockerfile
#
# Tomcat Dockerfile
#

# Pull base image.
FROM private-registry:5000/sunjdk8

# Define working directory.
WORKDIR /data

RUN cd /tmp
RUN curl http://apache.fayea.com/tomcat/tomcat-8/v8.0.15/bin/apache-tomcat-8.0.15.tar.gz > /tmp/tomcat.tar.gz
RUN tar zxf /tmp/tomcat.tar.gz
RUN ls
RUN rm /tmp/tomcat.tar.gz
RUN mv apache-tomcat* /usr/local/tomcat/
RUN mkdir /tmp/tomcat

# Define commonly used JAVA_HOME variable
ENV CLASSPATH .:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:/usr/local/tomcat/bin/bootstrap.jar:/usr/local/tomcat/bin/tomcat-juli.jar
ENV CATALINA_HOME /usr/local/tomcat
ENV CATALINA_BASE /usr/local/tomcat
ENV CATALINA_TMPDIR /tmp/tomcat

ENTRYPOINT ["/usr/local/tomcat/bin/catalina.sh"]
CMD ["run"]

