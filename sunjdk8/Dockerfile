#
# Oracle Java 8 Dockerfile
# It's really painful to lost how to download java and install it. Sorry for that.

# Pull base image.
FROM private-registry:5000/sunjdk8

# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/java/jdk1.8.0_25
ENV CLASSPATH .:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

# Define default command.
CMD ["bash"]
