# Dockerfile (./docker/app/Dockerfileなどに置くのがおすすめ)
FROM php:8.2-fpm
EXPOSE 5173

# システムツールとPHP拡張のインストール
RUN apt-get update && apt-get install -y \
    git \
    curl \
    unzip \
    zip \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    && docker-php-ext-install pdo_mysql zip mbstring exif pcntl bcmath

# Composerのインストール
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

# 作業ディレクトリ
WORKDIR /var/www

# 権限調整（任意）
RUN useradd -G www-data,root -u 501 -d /home/laravel laravel \
    && mkdir -p /home/laravel \
    && chown -R laravel:laravel /var/www /home/laravel

USER laravel