FROM php:7-fpm-alpine

RUN apk update 

# Install dependincies ################################################################################################
RUN apk add shadow git curl libpng-dev zip unzip libzip-dev libpng libpng-dev jpeg-dev libjpeg-turbo-dev libwebp-dev\
    libjpeg zlib-dev libxpm-dev freetype-dev libmemcached-dev $PHPIZE_DEPS

RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install pdo pdo_mysql gd zip exif opcache calendar redis

RUN pecl install xdebug memcached redis

RUN docker-php-ext-enable xdebug memcached redis

RUN curl -s http://getcomposer.org/installer | php && \
  echo "export PATH=${PATH}:/var/www/vendor/bin" >> ~/.bashrc && \
  mv composer.phar /usr/local/bin/composer
#######################################################################################################################

# Install dependincies ################################################################################################
RUN apk add zsh
RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true
#######################################################################################################################

# Solve permissions problems ##########################################################################################
RUN userdel www-data && rm -r /home/www-data
RUN useradd -m www-data -u 1000
RUN chown www-data:www-data /var/www
USER www-data
#######################################################################################################################

# Create aliases ######################################################################################
RUN echo 'alias art="php artisan"' >> ~/.zshrc
RUN echo 'alias test="clear && php artisan test"' >> ~/.zshrc
#######################################################################################################################

EXPOSE 9000
