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

FROM nginx:1.19-alpine

ARG PROJECT_USER

RUN addgroup -g "1000" -S "${PROJECT_USER}" && \
    adduser -u "1000" -S -D "${PROJECT_USER}" -G "${PROJECT_USER}"

RUN rm -f "/docker-entrypoint.d/10-listen-on-ipv6-by-default.sh"
