FROM debian:sid
MAINTAINER Bradley Jones <jones.bradley@me.com>

RUN apt-get update && apt-get install -y \
  ca-certificates \
  isync \
  && rm -rf /var/lib/apt/lists/*

