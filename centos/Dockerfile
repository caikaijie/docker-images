FROM centos:7
MAINTAINER KAIJIE CAI <caikaijie@gmail.com>

# aliyun mirrors
RUN yum install -y wget; \
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup; \
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo; \
wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo; \
yum clean all; \
mkdir -p ~/.pip/; \
echo '[global]' > ~/.pip/pip.conf; \
echo 'index-url = http://mirrors.aliyun.com/pypi/simple/' >> ~/.pip/pip.conf; \
echo '[install]' >> ~/.pip/pip.conf; \
echo 'trusted-host=mirrors.aliyun.com' >> ~/.pip/pip.conf;

# basic tools
RUN yum install -y net-tools telnet iftop nmap-ncat lsof; \
yum clean all;

