# Version: 1.5
FROM petre/oracle_jre:7u79

RUN rpm --import https://packages.elasticsearch.org/GPG-KEY-elasticsearch \
	&& echo "[logstash-1.5]" > /etc/yum.repos.d/logstash.repo \
	&& echo "name=Logstash repository for 1.5.x packages" >> /etc/yum.repos.d/logstash.repo \
	&& echo "baseurl=http://packages.elasticsearch.org/logstash/1.5/centos" >> /etc/yum.repos.d/logstash.repo \
	&& echo "gpgcheck=1" >> /etc/yum.repos.d/logstash.repo \
	&& echo "gpgkey=http://packages.elasticsearch.org/GPG-KEY-elasticsearch" >> /etc/yum.repos.d/logstash.repo \
	&& echo "enabled=1" >> /etc/yum.repos.d/logstash.repo \
	&& yum install -y logstash \
	&& yum clean all

ENV PATH /opt/logstash/bin:$PATH

COPY ./docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["logstash"]