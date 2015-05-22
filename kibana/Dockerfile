# Version: 4.0.2
FROM petre/gosu:1.4

ENV KIBANA_VERSION 4.0.2

# add our user and group first to make sure their IDs get assigned consistently
RUN groupadd -r kibana && useradd -r -d /opt/kibana -g kibana kibana -s /sbin/nologin

RUN curl -o "/kibana-$KIBANA_VERSION-linux-x64.tar.gz" -SL "https://download.elastic.co/kibana/kibana/kibana-$KIBANA_VERSION-linux-x64.tar.gz" \
	&& yum install -y tar \
	&& tar xzf "/kibana-$KIBANA_VERSION-linux-x64.tar.gz" \
	&& mv /kibana-$KIBANA_VERSION-linux-x64 /opt/kibana \
	&& rm -f "/kibana-$KIBANA_VERSION-linux-x64.tar.gz" \
	&& chown -R kibana:kibana /opt/kibana \
	&& yum remove -y tar && yum clean all

ENV PATH /opt/kibana/bin:$PATH

COPY ./docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["kibana"]