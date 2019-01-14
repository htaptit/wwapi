FROM node:8.14.0-jessie

RUN apt-get update
RUN apt-get install -y supervisor
RUN npm install pm2 -g && pm2 update && npm install loopback-cli -g --unsafe-perm

# Supervisor conf
RUN echo "[supervisord]" >> /etc/supervisor/supervisord.conf
RUN echo "nodaemon = true" >> /etc/supervisor/supervisord.conf
RUN echo "user = root" >> /etc/supervisor/supervisord.conf

# Supervisor npm
RUN echo "[program:npm]" >> /etc/supervisor/supervisord.conf
RUN echo "directory=/src" >> /etc/supervisor/supervisord.conf
RUN echo "command=/usr/local/bin/npm start" >> /etc/supervisor/supervisord.conf
RUN echo "stopasgroup=true" >> /etc/supervisor/supervisord.conf
RUN echo "autostart=true" >> /etc/supervisor/supervisord.conf

RUN mkdir -p /src

WORKDIR /src

EXPOSE 3000

CMD ["/usr/bin/supervisord"]