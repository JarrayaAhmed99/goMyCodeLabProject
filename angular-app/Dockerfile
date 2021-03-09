#app debuging
FROM node:latest as node
WORKDIR /app
COPY ./angular-app/package.json .
RUN npm install
COPY ./angular-app/ .
RUN npm run build --prod
#app deployment 
FROM nginx:alpine
COPY --from=node /app/dist /usr/share/nginx/html
