FROM nginx

RUN apt update && apt install openssh-server -y

RUN mkdir /var/run/sshd
RUN echo 'root:redhat' | chpasswd

EXPOSE 22

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
CMD [ "/usr/sbin/sshd", "-D"]