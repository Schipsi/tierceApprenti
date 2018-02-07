FROM debian:jessie

MAINTAINER Thibaut JUSTON <thibaut.juston@gmail.com>

RUN apt-get update && apt-get install -y \
    nginx

ADD nginx.conf /etc/nginx/
ADD tierceApprenti.conf /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/[YOUR_PROJECT].conf /etc/nginx/sites-enabled/[YOUR_PROJECT]
RUN rm /etc/nginx/sites-enabled/default

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 501 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
