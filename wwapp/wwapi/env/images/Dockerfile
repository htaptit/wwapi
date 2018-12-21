FROM node:8.14.0-jessie

RUN npm install pm2 -g && npm install loopback-cli -g --unsafe-perm

RUN mkdir -p /src

WORKDIR /src

EXPOSE 3000

CMD ["node", "index.js"]