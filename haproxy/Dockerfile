FROM kunkka/centos-systemd:7
MAINTAINER KAIJIE CAI <caikaijie@gmail.com>

RUN yum install -y less rsyslog haproxy; \
yum clean all; \
systemctl enable rsyslog.service; \
systemctl enable haproxy.service; \
echo '$ModLoad imudp' > /etc/rsyslog.d/haproxy.conf; \
echo '$UDPServerAddress 127.0.0.1' >> /etc/rsyslog.d/haproxy.conf; \
echo '$UDPServerRun 514' >> /etc/rsyslog.d/haproxy.conf; \
echo 'local2.*                       /var/log/haproxy.log' >> /etc/rsyslog.d/haproxy.conf;

EXPOSE 80
