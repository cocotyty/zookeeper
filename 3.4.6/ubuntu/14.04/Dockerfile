FROM ubuntu:14.04

RUN apt-get update && \
apt-get install -y curl openjdk-7-jre-headless python

# https://www.apache.org/mirrors/dist.html
RUN curl -fL http://apache.01link.hk/zookeeper/zookeeper-3.4.7/zookeeper-3.4.7.tar.gz | tar xzf - -C /opt && \
mv /opt/zookeeper-3.4.7 /opt/zookeeper

VOLUME /tmp/zookeeper

COPY entrypoint.sh /

ENTRYPOINT ["/entrypoint.sh"]

ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/zookeeper/bin

CMD ["zkServer.sh", "start-foreground"]
