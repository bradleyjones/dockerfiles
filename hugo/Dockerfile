FROM debian:stretch
MAINTAINER Bradley Jones <jones.bradley@me.com>

ENV VERSION 0.27.1

ADD https://github.com/gohugoio/hugo/releases/download/v${VERSION}/hugo_${VERSION}_Linux-64bit.deb /tmp/hugo.deb

RUN dpkg -i /tmp/hugo.deb \
  && rm /tmp/hugo.deb

ENTRYPOINT ["/usr/local/bin/hugo"]
