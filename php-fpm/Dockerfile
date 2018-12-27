FROM php:7.1-fpm

ENV WORK_DIR /opt/project

RUN apt-get update && apt-get install -y zlibc zlib1g zlib1g-dev \
    && docker-php-ext-install pdo pdo_mysql zip

EXPOSE 9000

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    &&  php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php composer-setup.php --install-dir=/usr/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

WORKDIR $WORK_DIR
