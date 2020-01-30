FROM debian:10
LABEL MAINTAINER="Guillem <gulopez76@gmail.com>"
EXPOSE 80
USER root

RUN apt-get update && \
    apt-get -y install libapache2-mod-php apache2 php php-common && \
    apt-get clean

COPY dokuwiki-stable.tgz /var/www/html/

RUN tar xvf /var/www/html/dokuwiki-stable.tgz -C /var/www/html/

RUN mv /var/www/html/dokuwiki-2018-04-22b/* /var/www/html/
RUN mv /var/www/html/dokuwiki-2018-04-22b/.ht* /var/www/html/

RUN chown -R www-data:www-data /var/www/html/*

ENTRYPOINT [ "/usr/sbin/apachectl", "-D", "FOREGROUND" ]



