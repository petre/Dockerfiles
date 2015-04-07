# Version: 0.5
FROM petre/gosu:1.3

RUN yum install -y wget
RUN wget --no-check-certificate --no-cookies --header \
  "Cookie: oraclelicense=accept-securebackup-cookie" \
  http://download.oracle.com/otn-pub/java/jdk/7u75-b13/jdk-7u75-linux-x64.rpm
RUN rpm -ivh jdk-7u75-linux-x64.rpm
RUN rm jdk-7u75-linux-x64.rpm

# set Java environment variables
ENV JAVA_HOME /usr/java/jdk1.7.0_75
ENV PATH $JAVA_HOME/bin:$PATH