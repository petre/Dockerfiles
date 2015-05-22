# Version: 0.79
FROM petre/gosu:1.4

RUN curl -o /tmp/jdk-7u79-linux-x64.rpm -v -j -k -L -H \
	"Cookie: oraclelicense=accept-securebackup-cookie" \
	http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.rpm \
	&& yum localinstall -y /tmp/jdk-7u79-linux-x64.rpm \
	&& rm -f /tmp/jdk-7u79-linux-x64.rpm \
	&& yum clean all

# set Java environment variables
ENV JAVA_HOME /usr/java/jdk1.7.0_79
ENV PATH $JAVA_HOME/bin:$PATH