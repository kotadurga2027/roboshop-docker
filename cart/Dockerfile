FROM node:20.19-alpine3.21
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
ENV REDIS_HOST=redis \
    CATALOGUE_HOST=catalouge \
    CATALOGUE_PORT=8080
CMD ["node","server.js"]