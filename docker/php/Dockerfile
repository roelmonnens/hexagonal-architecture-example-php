FROM ubuntu:16.10

VOLUME ["/var/www"]

RUN apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get install -y \
      apache2 \
      php \
      php-cli \
      libapache2-mod-php \
      php-apcu \
      php-apcu-bc \
      php-gd \
      php-json \
      php-curl \
      php-ldap \
      php-mbstring \
      php-mysql \
      php-opcache \
      php-pgsql \
      php-sqlite3 \
      php-xml \
      php-xsl \
      php-zip \
      php-soap \
      php-xdebug \
      curl \
      composer

COPY apache_default /etc/apache2/sites-available/000-default.conf
COPY run /usr/local/bin/run
RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod +x /usr/local/bin/symfony
RUN chmod +x /usr/local/bin/run
RUN a2enmod rewrite
WORKDIR /var/www/html
EXPOSE 80
CMD ["/usr/local/bin/run"]