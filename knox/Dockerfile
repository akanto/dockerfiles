FROM centos:7

ADD repo/hdp.repo /etc/yum.repos.d/HDP.repo
ADD repo/hdp-utils.repo /etc/yum.repos.d/HDP-utils.repo

RUN yum install -y java-1.8.0 which
RUN yum install -y knox --nogpgcheck

ENV JAVA_HOME /usr/lib/jvm/jre

