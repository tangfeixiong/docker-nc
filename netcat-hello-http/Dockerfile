# FROM gliderlabs/alpine:edge
FROM docker.io/alpine
MAINTAINER tangfeixiong <tangfx128@gmail.com>
# ENV APK_REPO_OPTS "--repository=http://mirrors.aliyun.com/alpine/edge/main"
# ENV APK_REPO_OPTS "--repository=http://mirrors.aliyun.com/alpine/edge/community"
# ENV APK_REPO_OPTS "--repository=http://mirrors.aliyun.com/alpine/edge/testing"
# ENV APK_REPO_OPTS "--repository=http://mirrors.aliyun.com/alpine/latest-stable/main"
RUN ( [[ -n $APK_REPO_OPTS ]] && apk add bash ca-certificates curl libc6-compat netcat-openbsd --update-cache $APK_REPO_OPTS --allow-untrusted \
  || ( sed -i -e 's/dl-cdn/dl-4/g' /etc/apk/repositories \
  && apk add --update --no-cache bash ca-certificates curl libc6-compat netcat-openbsd ) ) \
  && rm -rf /var/cache/apk/* \
  && echo "<html><head><title>welcome</title></head><body><h1>hello world</h1></body></html>" >> /tmp/site/index.html
VOLUME /tmp/site
EXPOSE 80
CMD while true; do nc -l 80 < /tmp/site/index.html; done
