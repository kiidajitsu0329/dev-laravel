# コンテナのベースとしてamazonlinux:2023を指定
FROM amazonlinux:2023

RUN yum -y update

RUN yum -y install unzip \
    wget

# php、モジュール関連インストール
RUN yum -y install php less php-intl \
    php-cli php-json php-common php-devel php-fpm \
    php-gd php-mysqlnd php-mbstring php-pdo php-xml

# unix socket
RUN mkdir /var/run/php-fpm
VOLUME [ "/var/run/php-fpm" ]

RUN echo 'short_open_tag = On' >> /etc/php.ini
RUN echo 'date.timezone = Asia/Tokyo' >> /etc/php.ini
EXPOSE 9000

ENTRYPOINT /usr/sbin/php-fpm -F

# composerインストール
WORKDIR /tmp
RUN wget https://getcomposer.org/installer -O composer-installer.php
RUN php composer-installer.php --filename=composer --install-dir=/usr/local/bin
RUN composer self-update

# nodeのインストール
RUN curl -fsSL https://rpm.nodesource.com/setup_18.x | bash -
RUN yum -y install nodejs

# コンテナのディレクトリ指定
WORKDIR /var/www/vhosts/test
