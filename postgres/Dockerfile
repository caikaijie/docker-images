FROM kunkka/centos-systemd:7
MAINTAINER KAIJIE CAI <caikaijie@gmail.com>

RUN yum install -y https://download.postgresql.org/pub/repos/yum/9.6/redhat/rhel-7-x86_64/pgdg-centos96-9.6-3.noarch.rpm; \
yum install -y postgresql96-server postgresql96-contrib; \
yum clean all;

EXPOSE 5432
