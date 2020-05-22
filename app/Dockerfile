FROM php:7-fpm-alpine 

RUN apk add mysql-client --no-cache
RUN docker-php-ext-install pdo pdo_mysql

RUN wget https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer -O - -q | php -- --quiet
RUN ./composer.phar create-project --prefer-dist laravel/laravel app 

EXPOSE 8000 9000
ENTRYPOINT ["php", "app/artisan", "serve", "--host", "0.0.0.0"]

