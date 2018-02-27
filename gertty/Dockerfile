FROM python:alpine
MAINTAINER Bradley Jones <jones.bradley@me.com>

RUN apk --update add git openssh && \
    rm -rf /var/lib/apt/lists/* && \
    rm /var/cache/apk/*

RUN git clone https://github.com/openstack/gertty /tmp/gertty && \
  pip install /tmp/gertty && \
  rm -rf /tmp/gertty


