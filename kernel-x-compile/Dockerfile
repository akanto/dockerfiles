FROM centos:7

RUN yum install -y bison flex gperf libtool texinfo gcc gcc-c++ gmp-devel wget which bzip2 help2man patch make ncurses-devel file

# wget http://crosstool-ng.org/download/crosstool-ng/crosstool-ng-1.22.0.tar.bz2
ADD deps/crosstool-ng-1.22.0.tar.bz2 /opt

RUN cd /opt/crosstool-ng && ./configure --prefix=/opt/crosstool-ng && make && make install && cp ct-ng.comp /etc/bash_completion.d/

ENV PATH=$PATH:/opt/crosstool-ng/bin

# ct-ng menuconfig
RUN mkdir /opt/crosstool-ng-config
ADD config/crostool-ng.config /opt/crosstool-ng-config/.config

RUN cd /opt/crosstool-ng-config &&  ct-ng build
