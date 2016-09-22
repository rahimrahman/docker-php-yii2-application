FROM wodby/nginx-php-7-alpine

RUN mkdir -p /var/www/html
ADD yii2-basic /var/www/html
RUN mkdir -p /var/www/html/runtime
RUN chmod 777 -R /var/www/html/runtime
RUN chown nginx.nginx -R /var/www/html/runtime
RUN chmod 777 -R /var/www/html/web/assets
RUN chown nginx.nginx -R /var/www/html/web/assets
RUN chmod 755 -R /var/www/html/yii

COPY nginx.conf /etc/nginx/conf.d/vhost.conf
COPY php-fpm.conf /etc/php7/php-fpm.conf

RUN /usr/local/bin/composer global require "fxp/composer-asset-plugin:^1.2.0";
RUN cd /var/www/html; /usr/local/bin/composer install --ignore-platform-reqs --prefer-dist
