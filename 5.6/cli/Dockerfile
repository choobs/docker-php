FROM alpine:latest
MAINTAINER Erik DeLamarter <erik.delamarter@choobs.com>

RUN apk add --update \
		git \
		php \
		php-ctype \
		php-json \
		php-openssl \
		php-phar \
		php-xml \
		&& rm -rf /var/cache/apk/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]