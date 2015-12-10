#
# Java Dockerfile
#
#

# Pull base image.
FROM centos:centos7
MAINTAINER renpeng.shang<renpeng.shang@woqu.com>

ADD jdk.rpm /tmp/jdk.rpm
RUN rpm -ivh /tmp/jdk.rpm && rm -f /tmp/jdk.rpm

ENV JAVAVERSION 8
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8
ENV JAVA_HOME /usr/java/jdk1.8.0_31
ENV JRE_HOME /usr/java/jdk1.8.0_31/jre
ENV PATH $PATH:$JAVA_HOME/bin

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Define default command.
CMD ["bash"]
