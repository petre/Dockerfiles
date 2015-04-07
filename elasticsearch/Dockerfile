# Version: 0.0.1
FROM petre/oracle_java:7u75

# add our user and group first to make sure their IDs get assigned consistently
#RUN groupadd -r elasticsearch && useradd -r -g elasticsearch elasticsearch

ENV ELASTICSEARCH_VERSION 1.5
ENV ES_GROUP elasticsearch
ENV ES_USER elasticsearch

RUN rpm --import https://packages.elasticsearch.org/GPG-KEY-elasticsearch
RUN echo "[elasticsearch-$ELASTICSEARCH_VERSION]" > /etc/yum.repos.d/elasticsearch.repo
RUN echo "name=Elasticsearch repository for $ELASTICSEARCH_VERSION packages" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "baseurl=http://packages.elasticsearch.org/elasticsearch/$ELASTICSEARCH_VERSION/centos" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "gpgcheck=1" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "gpgkey=http://packages.elasticsearch.org/GPG-KEY-elasticsearch" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "enabled=1" >> /etc/yum.repos.d/elasticsearch.repo
RUN yum install -y elasticsearch

ENV PATH /usr/share/elasticsearch/bin:$PATH

VOLUME /usr/share/elasticsearch/data
VOLUME /usr/share/elasticsearch/config

RUN /usr/share/elasticsearch/bin/plugin --install mobz/elasticsearch-head

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

EXPOSE 9200

CMD ["elasticsearch"]

#sudo docker run -t -i -p 127.0.0.1:9200:9200 -v /data/es0:/usr/share/elasticsearch/data -v /data/docker_configs/es0:/usr/share/elasticsearch/config petre/elasticsearch:1.5 /bin/bash