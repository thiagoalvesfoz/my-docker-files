FROM php:7.4-cli

WORKDIR /var/www

# install packages base
RUN apt-get update && \
    apt-get install libzip-dev -y && \
    docker-php-ext-install zip

# Install Composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');"

# Install Laravel
RUN php composer.phar create-project laravel/laravel laravel

ENTRYPOINT ["php", "laravel/artisan", "serve"]
CMD ["--host=0.0.0.0"]