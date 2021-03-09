FROM node:latest
WORKDIR /app
COPY ./express-server/package.json /app
RUN npm install
#COPY . .
COPY ./express-server/ .
EXPOSE 3000
CMD ["node","server.js"]
