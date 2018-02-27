FROM ubuntu:14.04
MAINTAINER Bradley Jones <jones.bradley@me.com>

# Install packages
RUN apt-get update && apt-get install -y \
  git \
  python-dev \
  python-pip \
&& rm -rf /var/lib/apt/lists/*

RUN pip install \
  wrapt \
  alembic \
  oslo.i18n \
  oslo.config \
  oslo.utils \
  oslo.concurrency \
  oslo.log \
  oslo.policy \
  neutron_lib \
  greenlet \
  keystoneauth1 \
  singledispatch \
  python-novaclient \
  pymysql

# Get git repos for devstack & neutron
RUN git clone https://git.openstack.org/openstack/neutron /root/neutron

# Install neutron
RUN pip install /root/neutron/

ENTRYPOINT ["neutron-db-manage", "--database-connection", "mysql+pymysql://root:stackdb@neutron-db/neutron?charset=utf8"]
CMD ["current"]
