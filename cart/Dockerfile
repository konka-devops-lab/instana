FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/node-runtime:20-alpine-3.23.2

WORKDIR /opt/server

COPY node_modules ./node_modules
COPY server.js .

CMD ["node", "server.js"]