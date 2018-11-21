FROM library/alpine:latest
MAINTAINER "Arulkumar"

RUN apk update
RUN apk add nginx
ADD nginx.conf /etc/nginx/nginx.conf

ADD ./www-data /www-data

EXPOSE 80
CMD ["nginx"]
