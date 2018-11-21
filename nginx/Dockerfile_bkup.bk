# Version: 0.0.1
FROM library/alpine:latest
MAINTAINER "Arulkumar"
RUN apk update
RUN apk add nginx
RUN mkdir -p /usr/share/nginx/html/
RUN echo 'Hello World ' \
>/usr/share/nginx/html/index.html
EXPOSE 80
RUN apk add openrc
CMD rc-service nginx start
