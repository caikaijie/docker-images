FROM kunkka/devbase
MAINTAINER KAIJIE CAI <caikaijie@gmail.com>

COPY build-tools /build-tools

# git
RUN chmod +x /build-tools/install-git; /build-tools/install-git; \
# vim
chmod +x /build-tools/install-vim; /build-tools/install-vim; \
# sudo
yum install -y sudo; \
# clean
yum clean all; \
rm -rf /build-tools

ONBUILD ARG rootpasswd=root
ONBUILD ARG user=dev
ONBUILD ARG userid
ONBUILD ARG userpasswd=dev
ONBUILD ARG group=
ONBUILD ARG groupid

COPY devenvbase-tools /devenvbase-tools

# avoid: sudo: sorry, you must have a tty to run sudo
RUN sed -i -e "s/Defaults    requiretty.*/ #Defaults    requiretty/g" /etc/sudoers

ONBUILD RUN chmod +x /devenvbase-tools/init; \
rootpasswd=$rootpasswd user=$user group=$group userpasswd=$userpasswd userid=$userid groupid=$groupid /devenvbase-tools/init; \
# clean
rm -rf /devenvbase-tools

ONBUILD USER $user

# dotfiles
ONBUILD RUN mkdir -p ~/code; \
git clone https://github.com/mathiasbynens/dotfiles.git ~/code/dotfiles; \
source ~/code/dotfiles/bootstrap.sh -f;

CMD ["/bin/bash"]
