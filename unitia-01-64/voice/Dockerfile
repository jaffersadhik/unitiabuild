FROM centos:7

MAINTAINER Tim Akinbo <takinbo@timbaobjects.com>


RUN yum update -y
RUN yum install -y bzip2
RUN yum install -y kernel-devel kernel-headers
#RUN cd /lib/modules/`uname -r`
RUN ls -l
RUN yum install -y wget
RUN cd /usr/local/src 
RUN wget https://downloads.asterisk.org/pub/telephony/asterisk/asterisk-16-current.tar.gz 
RUN wget https://downloads.asterisk.org/pub/telephony/dahdi-linux-complete/dahdi-linux-complete-current.tar.gz 
RUN wget https://downloads.asterisk.org/pub/telephony/dahdi-linux/dahdi-linux-current.tar.gz 
RUN wget https://downloads.asterisk.org/pub/telephony/dahdi-tools/dahdi-tools-current.tar.gz 
RUN wget https://downloads.asterisk.org/pub/telephony/libpri/libpri-current.tar.gz
RUN yum install -y gcc-c++ make
RUN cd /usr/local/src
RUN ls -lrt
RUN tar -zxvf asterisk-16-current.tar.gz 
RUN ls -lrt
RUN pwd \
    && tar -zxvf dahdi-linux-complete-current.tar.gz \
    && tar -zxvf dahdi-linux-current.tar.gz \
    && tar -zxvf dahdi-tools-current.tar.gz \
    && tar -zxvf libpri-current.tar.gz \
    && ls -lrt /usr/local/src \
    && pwd \
    && ls -lrt \
    && mv dahdi-linux-complete-3.1.0+3.1.0 /usr/src/. \
    && mv libpri-1.6.0 /usr/src/. \
    && mv dahdi-linux-3.1.0 /usr/src/. \
    && mv dahdi-tools-3.1.0 /usr/src/. \
    && mv asterisk-16.16.1 /usr/src/. 

RUN ls -lrt /usr/lib/modules
RUN ls -lrt /lib/modules
RUN cd /usr/src/asterisk-16.16.1 \
    && ./configure \
    && make \
    && make install

