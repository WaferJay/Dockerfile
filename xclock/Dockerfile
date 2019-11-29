FROM alpine:latest

MAINTAINER WaferJay

#ARG REPO=mirrors.aliyun.com

ARG REPO

RUN [[ ${REPO} ]] && sed -i \
    "s/dl-cdn.alpinelinux.org/${REPO}/g" /etc/apk/repositories; \
    apk --no-cache add xclock

ENTRYPOINT ["/usr/bin/xclock"]
