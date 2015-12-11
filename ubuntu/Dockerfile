
FROM ubuntu:14.04
MAINTAINER phyng

ENV DEBIAN_FRONTEND noninteractive

COPY source.list /etc/apt/sources.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 16126D3A3E5C1192
RUN apt-get update && apt-get install -y \
    htop tree curl wget git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
