FROM ubuntu:latest
MAINTAINER Bradley Jones <jones.bradley@me.com>

RUN apt-get update && apt-get install -y \
  python-pip \
  qemu-utils \
  sudo \
  curl \
  kpartx \
  git \
  && rm -rf /var/lib/apt/lists/*

RUN pip install diskimage-builder

ENTRYPOINT ["/usr/local/bin/disk-image-create"]
