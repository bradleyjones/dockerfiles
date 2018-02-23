FROM ubuntu:latest
MAINTAINER Bradley Jones <jones.bradley@me.com>

RUN apt-get update && apt-get install -y \
  bitlbee-libpurple \
  libpurple-dev \
  libjson-glib-dev \
  libglib2.0-dev \
  libprotobuf-c-dev \
  protobuf-c-compiler \
  mercurial \
  make \
  && rm -rf /var/lib/apt/lists/*

RUN hg clone https://bitbucket.org/EionRobb/purple-hangouts/ \
  && cd purple-hangouts \
  && make \
  && make install

#RUN chown -R bitlbee:bitlbee /var/lib/bitlbee*

EXPOSE 6667
VOLUME /var/lib/bitlbee
#RUN touch /var/run/bitlbee.pid && \
  #chown bitlbee:bitlbee /var/run/bitlbee.pid && \
  #chown -R bitlbee:bitlbee /var/lib/bitlbee*
#USER bitlbee

ENTRYPOINT [ "bitlbee", "-nF" ]
