FROM nginx:1.21.3-alpine

COPY start /usr/local/bin/start
COPY config/bx /etc/nginx/bx
COPY config/nginx.conf /etc/nginx/nginx.conf
COPY config/mime.types /etc/nginx/mime.types
COPY ssl /etc/nginx/ssl

RUN apk update && apk add \
    openssl \
    && rm -rf /var/cache/apk/* \
    && chmod ugo+x /usr/local/bin/start

CMD ["/usr/local/bin/start"]