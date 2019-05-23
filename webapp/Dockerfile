FROM ubuntu

RUN apt-get update \
   && apt-get install -y apache2 openssh-server vim sudo
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

COPY index.html /var/www/html/
RUN useradd -u 12345 -g users -d /home/igorloza -s /bin/bash -p $(echo igorloza | openssl passwd -1 -stdin) igorloza

COPY flag.txt /tmp/
COPY startup.sh /tmp/
RUN chown root /tmp/flag.txt
RUN chmod 640 /tmp/flag.txt
RUN usermod -aG sudo igorloza

WORKDIR /var/www/html
ENTRYPOINT ["/bin/bash", "/tmp/startup.sh"]
CMD ["apachectl", "-D", "FOREGROUND"]
EXPOSE 80
EXPOSE 22
#RUN service ssh start
#CMD ["/usr/sbin/sshd", "-D"]
