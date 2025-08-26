FROM node:20-alpine3.21 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install


FROM node:20-alpine3.21
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
ENV MONGO=true \
    REDIS_URL='redis://redis:6379' \
    MONGO_URL="mongodb://mongodb:27017/users"
USER roboshop
COPY --from=builder opt/server /opt/server
CMD ["node","server.js"]



# FROM node:20-alpine3.21
# RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# RUN chown -R roboshop:roboshop /opt/server
# ENV MONGO=true \
#     REDIS_URL='redis://redis:6379' \
#     MONGO_URL="mongodb://mongodb:27017/users"
# USER roboshop
# CMD ["node","server.js"]

