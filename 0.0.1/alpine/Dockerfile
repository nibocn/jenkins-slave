FROM nibo/java:8u171-jre
MAINTAINER Richard <nibocn@gmail.com>

ENV TZ=Asia/Shanghai

RUN apk add --no-cache --update-cache docker openssh-server && \
    ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' && \
    echo "root:root" | chpasswd && \
    rm -rf /var/cache/apk/*

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

