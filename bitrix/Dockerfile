FROM nginx:1.21.3-alpine

COPY start /usr/local/bin/start
COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY nginx/conf.d /etc/nginx/conf.d
COPY nginx/sites-available /etc/nginx/sites-available
COPY ssl /etc/nginx/ssl

RUN apk update && apk add \
    openssl \
    && rm -rf /var/cache/apk/* \
    && chmod ugo+x /usr/local/bin/start

CMD ["/usr/local/bin/start"]