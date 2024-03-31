FROM node:latest as builder

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

FROM node:latest

WORKDIR /usr/src/app

COPY --from=builder /usr/src/app .

EXPOSE 8080

CMD ["node", "server.js"]