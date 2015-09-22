FROM debian:jessie
MAINTAINER Samuel Tardieu, sam@rfc1149.net

RUN apt-get update
RUN apt-get -y dist-upgrade
RUN apt-get -y install python3.4 autoconf automake build-essential wget bison flex texinfo virtualenv

RUN useradd -m -c "se202" -s /bin/bash se202

RUN cd /tmp && wget https://github.com/pablooliveira/irvm/archive/v0.0.3.tar.gz && \
    tar zxf v0.0.3.tar.gz && cd irvm-0.0.3 && \
    autoreconf -f -i && ./configure && make install && \
    cd /tmp && rm -rf v0.0.3.tar.gz irvm-0.0.3

VOLUME /work

USER se202
ENV PATH /home/se202/se202/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
RUN cd $HOME && virtualenv -p python3.4 se202
RUN pip install --upgrade pip && pip install grako ply
WORKDIR /work
