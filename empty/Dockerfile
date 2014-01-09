FROM mhamel/jboss7

RUN apt-get update

RUN apt-get install -y supervisor openssh-server

RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor

ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN echo 'root:rhemubuntu' | chpasswd

RUN sed -i 's/enable-welcome-root="true"/enable-welcome-root="false"/' /usr/local/share/jboss/standalone/configuration/standalone.xml

CMD ["/usr/bin/supervisord"]
