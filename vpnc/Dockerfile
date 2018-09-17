#FROM armv7/armhf-debian
FROM debian:latest
MAINTAINER Bradley Jones <jones.bradley@me.com>

RUN apt-get -y update && apt-get install -y vpnc openssh-server
ADD default.conf /etc/vpnc/default.conf
ADD authorized_keys /root/.ssh/authorized_keys

CMD ["/usr/sbin/vpnc"]
