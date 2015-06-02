# Version: 1.5.2
FROM petre/oracle_jre:7u79

ENV ELASTICSEARCH_VERSION 1.5.2

RUN yum localinstall -y https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-$ELASTICSEARCH_VERSION.noarch.rpm \
	&& yum clean all

ENV PATH /usr/share/elasticsearch/bin:$PATH
VOLUME /usr/share/elasticsearch/data
VOLUME /usr/share/elasticsearch/config

#Installing elasticsearch plugins
RUN /usr/share/elasticsearch/bin/plugin --install mobz/elasticsearch-head \
	&& /usr/share/elasticsearch/bin/plugin --install lmenezes/elasticsearch-kopf \
	&& /usr/share/elasticsearch/bin/plugin --install royrusso/elasticsearch-HQ

COPY ./docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

EXPOSE 9200 9300

CMD ["elasticsearch"]
