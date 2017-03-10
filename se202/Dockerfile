FROM debian:jessie
MAINTAINER Samuel Tardieu, sam@rfc1149.net

RUN apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y install python3.4 python3-pip autoconf automake build-essential wget bison flex texinfo virtualenv curl
RUN ln -s python3 /usr/bin/python && ln -s pip3 /usr/bin/pip
RUN pip install --upgrade pip && pip install grako ply

RUN cd /tmp && wget https://github.com/pablooliveira/irvm/archive/v0.0.3.tar.gz && \
    tar zxf v0.0.3.tar.gz && cd irvm-0.0.3 && \
    autoreconf -f -i && ./configure && make install && \
    cd /tmp && rm -rf v0.0.3.tar.gz irvm-0.0.3

ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV LANG en_US
ENV LC_ALL en_US.UTF-8
