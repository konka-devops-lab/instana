# FROM node:20-alpine
# RUN apk add --no-cache bash
# RUN mkdir /opt/server
# RUN adduser -D -h /opt/server roboshop
# RUN chown roboshop:roboshop -R /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY server.js .
# RUN npm install --omit=dev
# USER roboshop
# EXPOSE 8080
# CMD ["node", "server.js"]

FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/node-runtime:20-alpine

WORKDIR /opt/server

COPY node_modules ./node_modules
COPY server.js .

CMD ["node", "server.js"]