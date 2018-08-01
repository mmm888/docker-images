From alpine

ENV NSD_VERSION 4.1.22

RUN apk add --no-cache --virtual .builddeps build-base bind-tools openssl openssl-dev libevent-dev && \
    cd /root && \
    wget "https://www.nlnetlabs.nl/downloads/nsd/nsd-${NSD_VERSION}.tar.gz" && \
    tar zxvf nsd-${NSD_VERSION}.tar.gz && \
    cd nsd-${NSD_VERSION} && \
    ./configure && \
    make -j4 && \
    make install && \
    adduser -s /sbin/nologin -D -H nsd && \
    mkdir /etc/nsd/master /etc/nsd/var/db /etc/nsd/var/run -p && \
    chown nsd: /etc/nsd/ -R && \
    nsd-control-setup && \
    apk del build-base

EXPOSE 53/udp

ENTRYPOINT ["nsd", "-d"]
