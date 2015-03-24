# Version: 0.0.1
FROM petre/oracle_java:7u75
MAINTAINER Petre Ghita "petre.ghita@gmail.com"
ENV ELASTICSEARCH_VERSION 1.5
RUN rpm --import https://packages.elasticsearch.org/GPG-KEY-elasticsearch
RUN echo "[elasticsearch-$ELASTICSEARCH_VERSION]" > /etc/yum.repos.d/elasticsearch.repo
RUN echo "name=Elasticsearch repository for $ELASTICSEARCH_VERSION packages" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "baseurl=http://packages.elasticsearch.org/elasticsearch/$ELASTICSEARCH_VERSION/centos" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "gpgcheck=1" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "gpgkey=http://packages.elasticsearch.org/GPG-KEY-elasticsearch" >> /etc/yum.repos.d/elasticsearch.repo
RUN echo "enabled=1" >> /etc/yum.repos.d/elasticsearch.repo
RUN yum install -y elasticsearch

EXPOSE 9200