# +----------------------------------------------------------------------------+
# |                                                                            |
# | This file is part of the Qunity package.                                   |
# |                                                                            |
# | Copyright (c) Rodion Kachkin <kyleRQWS@gmail.com>                          |
# |                                                                            |
# | For the full copyright and license information, please view the LICENSE    |
# | file that was distributed with this source code.                           |
# |                                                                            |
# +----------------------------------------------------------------------------+

FROM php:8.0-fpm-alpine

ARG PROJECT_USER

RUN addgroup -g "1000" -S "${PROJECT_USER}" && \
    adduser -u "1000" -S -D "${PROJECT_USER}" -G "${PROJECT_USER}"

RUN apk update

RUN curl -sS "https://getcomposer.org/installer" | \
    php -- --install-dir "/usr/local/bin" --filename "composer" --prefer-dist

RUN apk add --no-cache ${PHPIZE_DEPS} && \
    pecl install "xdebug" && docker-php-ext-enable "xdebug" && \
    docker-php-ext-install "opcache" && docker-php-ext-enable "opcache"
