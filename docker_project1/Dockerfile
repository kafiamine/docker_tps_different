# je me base sur l'image (officielle) la plus proche
FROM php:7.3-apache

RUN apt-get update \
    && apt-get install -y wget

#telecharger dokuwiki 
RUN wget -O /usr/src/dokuwiki-stable.tgz \
	https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz

RUN mkdir  -p /var/www/html \
    && cd /var/www/html \
    && tar --strip-components=1 -xavf /usr/src/dokuwiki-stable.tgz \
    && chown -R www-data:www-data .					
