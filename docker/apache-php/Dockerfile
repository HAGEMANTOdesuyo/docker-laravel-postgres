FROM php:7.4.9-apache
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
# RUNで指定したコマンドはイメージ作成時(=docker build時)に実行される
RUN apt-get update && \
  apt-get install -y libonig-dev \
  zip git && \
  # PHPのExtensionをインストール
  #docker-php-ext-install pdo_mysql mysqli mbstring
  docker-php-ext-install pdo_mysql mysqli
# ドキュメントルート変更
#RUN sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf
# Laravelで必要になるmodRewriteを有効化する
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite
# CMDで指定したコマンドはコンテナ開始時(=docker start時)/作成時(=docker run時)じ実行される
#CMD sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf

#EXPOSE 80
