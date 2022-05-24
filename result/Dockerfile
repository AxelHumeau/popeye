FROM node:12-alpine
EXPOSE 80
WORKDIR /home/popeye
COPY package.json .
RUN npm install
COPY . .
CMD ["node", "server.js"]
