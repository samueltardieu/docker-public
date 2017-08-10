FROM debian:jessie
MAINTAINER Samuel Tardieu <sam@rfc1149.net>
ENV DEBIAN_FRONTEND noninteractive

# Add backports and testing
RUN echo "deb http://ftp.debian.org/debian jessie-backports main" >> /etc/apt/sources.list
RUN echo "deb http://ftp.debian.org/debian testing main" >> /etc/apt/sources.list
ADD testing.pref /etc/apt/preferences.d/

# Install packages
RUN apt-get -qq update
RUN apt-get -y dist-upgrade
RUN apt-get --no-install-recommends -y install \
      build-essential ca-certificates clang clang-format-3.5 g++ \
      ccache autoconf automake libboost-all-dev flex bison
