# Version: 0.5
FROM petre/oracle_java:7u75

ENV SONAR_VERSION 4.5.4

RUN wget -O /etc/yum.repos.d/sonar.repo http://downloads.sourceforge.net/project/sonar-pkg/rpm/sonar.repo
RUN yum install -y sonar-$SONAR_VERSION

