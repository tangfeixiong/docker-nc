# FROM gliderlabs/alpine:edge
FROM docker.io/alpine
MAINTAINER tangfeixiong <tangfx128@gmail.com>
RUN apk add --update bash ca-certificates curl libc6-compat netcat-openbsd && rm -rf /var/cache/apk/*
RUN echo "<html><head><title>welcome</title></head><body><h1>hello world</h1></body></html>" >> /tmp/index.html
EXPOSE 80
CMD while true; do nc -l 80 < /tmp/index.html; done
