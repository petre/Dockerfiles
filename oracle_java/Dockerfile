# Version: 0.0.1
FROM centos:6
MAINTAINER Petre Ghita "petre.ghita@gmail.com"
RUN yum install -y wget
RUN wget --no-check-certificate --no-cookies --header \
  "Cookie: oraclelicense=accept-securebackup-cookie" \
  http://download.oracle.com/otn-pub/java/jdk/7u75-b13/jdk-7u75-linux-x64.rpm
RUN rpm -ivh jdk-7u75-linux-x64.rpm
