# DOCKER-VERSION 1.0.1
# VERSION        0.5

FROM 192.168.199.20:5000/java:1.8_31
MAINTAINER renpeng.shang <renpeng.shang@woqu.com>

ADD zookeeper-3.4.6 /opt/zookeeper
ADD start.sh /bin/start.sh

RUN cp /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
	&& mkdir -p /tmp/zookeeper

EXPOSE 2181 2888 3888 2182 2889 3889 2183 2890 3890

WORKDIR /opt/zookeeper

#VOLUME ["/opt/zookeeper/conf", "/tmp/zookeeper"]

#ENTRYPOINT ["/opt/zookeeper/bin/zkServer.sh"]
CMD ["/bin/start.sh"]
