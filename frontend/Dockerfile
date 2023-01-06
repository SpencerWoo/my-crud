# docker build . --no-cache -t frontend
# docker run -p 8080:80 -d frontend

FROM nginx:latest

WORKDIR /var/www/html/

COPY . /var/www/html
COPY ./default.conf /etc/nginx/conf.d/default.conf