#app debuging
FROM node:latest as node
WORKDIR /app
COPY ./package.json /app
RUN npm install
COPY . /app
#app deployment 
FROM nginx:alpine
COPY --from=node /app/dist /usr/share/nginx/html
