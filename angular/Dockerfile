
FROM node:10.24-alpine as node

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build
LABEL maintainer="Anthony GOUAT"


FROM nginx:1.27-alpine

COPY --from=node /app/nginx/ /etc/nginx

COPY --from=node /app/dist/ /usr/share/nginx/html

COPY entrypoint.sh /docker-entrypoint.d/entrypoint.sh
