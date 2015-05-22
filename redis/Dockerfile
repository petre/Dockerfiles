# Version: 2.8.19

FROM petre/gosu:1.4

ENV REDIS_VERSION 2.8.19

RUN yum install -y http://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm \
	&& yum install -y http://rpms.famillecollet.com/enterprise/remi-release-6.rpm \
	&& yum --enablerepo=remi install -y redis-$REDIS_VERSION \
	&& yum clean all \
	&& mkdir /data \
	&& chown redis:redis /data

VOLUME /data
WORKDIR /data
	
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh
ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["redis-server"]