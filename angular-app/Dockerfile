#app debuging
FROM node:latest as node
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . .
RUN npm run build --prod
#app deployment 
FROM nginx:alpine
COPY --from=node /app/dist /usr/share/nginx/html
