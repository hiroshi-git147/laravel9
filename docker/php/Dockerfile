# Dockerfileとは
# Dockerfileは、Dockerコンテナをビルドするための指示を含むテキストファイルです。

# Dockerfileを使用することで、特定の環境でアプリケーションを実行するために必要な手順を自動化することができます。

# Dockerfileは、コンテナ内にどのようなファイルや設定を配置するか、どのベースイメージを使用するか、どのコマンドを実行するかなど、コンテナの構築に関する情報を提供します。

# Dockerimage の指定
FROM php:8.0-fpm
COPY php.ini /usr/local/etc/php/

# Package & Library install
RUN apt-get update \
    && apt-get install -y zlib1g-dev mariadb-client vim libzip-dev \
    && docker-php-ext-install zip pdo_mysql

# Composer install
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV PATH $PATH:/composer/vendor/bin

# WorkDir Path setting
WORKDIR /var/www

# Laravel Package install
RUN composer global require "laravel/installer"
