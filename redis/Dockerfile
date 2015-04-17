# Version: 0.0.1

FROM centos:6

# add our user and group first to make sure their IDs get assigned consistently
RUN groupadd -r redis && useradd -r -g redis redis

ENV REDIS_VERSION 2.8.19

RUN yum install -y wget
RUN yum install -y epel-release
RUN wget http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN rpm -Uvh remi-release-6*.rpm

RUN yum --enablerepo=remi install -y redis

RUN mkdir /data && chown redis:redis /data
VOLUME /data
WORKDIR /data

#ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 6379
#CMD [ "redis-server" ]