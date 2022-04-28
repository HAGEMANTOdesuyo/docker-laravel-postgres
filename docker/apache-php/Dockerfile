FROM php:7.4-apache
# install composer
# マルチステージビルドを使用
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
# install Node.js
# マルチステージビルドを使用
# node.jsのversionに注意
# もしかしたら変更する必要があるかも
COPY --from=node:10.22 /usr/local/bin /usr/local/bin
COPY --from=node:10.22 /usr/local/lib /usr/local/lib
# RUNで指定したコマンドはイメージ作成時(=docker build時)に実行される
RUN apt-get update && \
  apt-get install -y libonig-dev libpq-dev \
  #apt-get install -y libonig-dev \
  zip git vim && \
  # PHPのExtensionをインストール
  #docker-php-ext-install pdo_mysql mysqli mbstring
  #docker-php-ext-install pdo_mysql mysqli
  docker-php-ext-install pdo_mysql mysqli pdo_pgsql
# ドキュメントルート変更
#RUN sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf
# Laravelで必要になるmodRewriteを有効化する
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite
# CMDで指定したコマンドはコンテナ開始時(=docker start時)/作成時(=docker run時)じ実行される
#CMD sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf

#EXPOSE 80
