FROM alpine:latest
MAINTAINER Erik DeLamarter <erik.delamarter@choobs.com>

RUN echo "@testing http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories
RUN apk add --update \
		git \
		php7@testing \
		php7-ctype@testing \
		php7-fpm@testing \
		php7-json@testing \
		php7-openssl@testing \
		php7-phar@testing \
		php7-xml@testing \
		&& rm -rf /var/cache/apk/*

RUN ln -s /usr/bin/php7 /usr/bin/php && ln -s /usr/sbin/php-fpm7 /usr/sbin/php-fpm && ln -s /etc/php7 /etc/php

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN set -ex \
		&& cd /etc/php \
		&& { \
				echo '[global]'; \
				echo 'error_log = /proc/self/fd/2'; \
				echo; \
				echo '[www]'; \
				echo '; if we send this to /proc/self/fd/1, it never appears'; \
				echo 'access.log = /proc/self/fd/2'; \
				echo; \
				echo 'clear_env = no'; \
				echo; \
				echo '; Ensure worker stdout and stderr are sent to the main error log.'; \
				echo 'catch_workers_output = yes'; \
			} | tee php-fpm.d/docker.conf \
			&& { \
				echo '[global]'; \
				echo 'daemonize = no'; \
				echo; \
				echo '[www]'; \
				echo 'listen = [::]:9000'; \
			} | tee php-fpm.d/zz-docker.conf

EXPOSE 9000
CMD ["php-fpm"]