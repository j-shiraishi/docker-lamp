FROM php:apache
MAINTAINER nino0813do

RUN apt-get update \
  && apt-get install -y \
    git \
    vim \
    less \
    tree \
    zip \
    unzip \
  --no-install-recommends && rm -r /var/lib/apt/lists/*

COPY ./php.ini /usr/local/etc/php/

COPY ./my-httpd.conf /etc/apache2/
