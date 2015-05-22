# Version: 0.79
FROM petre/gosu:1.4

RUN curl -o /jre-7u79-linux-x64.rpm -v -j -k -L -H "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jre-7u79-linux-x64.rpm
RUN yum localinstall -y /jre-7u79-linux-x64.rpm && yum clean all
RUN rm /jre-7u79-linux-x64.rpm

# set Java environment variables
ENV JAVA_HOME /usr/java/jre1.7.0_79
ENV PATH $JAVA_HOME/bin:$PATH
