FROM kunkka/centos:7
MAINTAINER KAIJIE CAI <caikaijie@gmail.com>

# development tools
RUN yum groupinstall -y "Development Tools"; \
yum install -y ruby;

# clean
RUN yum clean all; 

CMD ["/bin/bash"]
