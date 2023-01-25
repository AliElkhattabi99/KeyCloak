FROM node:18.13.0 as build
WORKDIR /usr/local/app
COPY ./ /usr/local/app/
RUN npm install --force
RUN npm run build
FROM nginx:latest
COPY --from=build /usr/local/app/dist/frontend /usr/share/nginx/html
COPY /default.conf  /etc/nginx/conf.d/default.conf
EXPOSE 80