FROM nibo/java:8u171-jdk
MAINTAINER Richard <nibocn@gmail.com>

ENV TZ=Asia/Shanghai

RUN apk add --no-cache --update-cache docker openssh \
    && ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' \
    && sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config \
    && echo "root:root" | chpasswd \
    && mkdir -p /opt/jenkins \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

VOLUME /opt/jenkins

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
