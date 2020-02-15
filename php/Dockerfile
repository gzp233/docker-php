FROM php:7.4-fpm

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apt/sources.list && \
    sed -i 's/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list && \
    sed -i 's/security.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list && \
    sed -i 's/security-cdn.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list

# 安装php相关
RUN set -xe; \
    apt-get update && apt-get install -y \
    apt-utils \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmagickwand-dev \
    libmagickcore-dev \
    libpng-dev \
    libonig-dev \
    libcurl4-openssl-dev \
    libzip-dev \
    pkg-config \
    zlibc \
    curl \
    git \
    imagemagick \
&& docker-php-ext-configure pdo_mysql \
&& docker-php-ext-install pdo_mysql \
&& pecl install redis \
    swoole \
    imagick  \
&& docker-php-ext-enable redis \
    swoole \
    imagick \
&& docker-php-ext-install \
    curl \
    intl \
    iconv \
    mbstring \
    pdo \
    pdo_mysql \
    pcntl \
    tokenizer \
    xml \
    zip \
    gd \
# 安装composer
&& php -r "copy('https://install.phpcomposer.com/installer', 'composer-setup.php');" \
&& php composer-setup.php \
&& php -r "unlink('composer-setup.php');" \
&& mv composer.phar /usr/local/bin/composer \
&& composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/



RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone

# ENV NODE_VERSION 10.9.0

RUN set -xe; \
    apt-get update && apt-get install -y \
        gnupg \
        python \
        nodejs \
        npm \
    && npm install -g yarn \
    && yarn config set registry 'https://registry.npm.taobao.org' \
    && npm install -g cnpm --registry=https://registry.npm.taobao.org

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
