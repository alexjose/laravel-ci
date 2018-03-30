FROM php:7.1

# Installing required packages
RUN apt-get update -yqq
RUN apt-get install gnupg git libcurl4-gnutls-dev libicu-dev libmcrypt-dev libvpx-dev libjpeg-dev libpng-dev libxpm-dev zlib1g-dev libfreetype6-dev libxml2-dev libexpat1-dev libbz2-dev libgmp3-dev libldap2-dev unixodbc-dev libpq-dev libsqlite3-dev libaspell-dev libsnmp-dev libpcre3-dev libtidy-dev -yqq

# Installing Node 8, Required for running NPM tests
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install nodejs -yqq

# Installing PHP extensions
RUN docker-php-ext-install mcrypt mbstring pdo_mysql curl json intl gd xml zip bz2 opcache

# Install XDebug
# TODO: Upgrade version when stable version release
RUN pecl install xdebug && pecl install mongodb
RUN docker-php-ext-enable xdebug mongodb

# Installing Composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
