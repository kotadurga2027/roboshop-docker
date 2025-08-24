FROM node:20.19-alpine3.21
RUN addugroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
RUN chown -R roboshop:roboshop /opt/server
ENV REDIS_HOST=redis \
    CATALOGUE_HOST=catalouge \
    CATALOGUE_PORT=8080
USER roboshop
CMD ["node","server.js"]