FROM alpine:3.6

LABEL maintainer="mritd <mritd1234@gmail.com>"

ARG TZ="Asia/Shanghai"

ENV TZ ${TZ}

ENV BROOK_VERSION 20171111 

RUN apk upgrade --update \
    && apk add bash tzdata wget \
    && wget --no-check-certificate https://github.com/txthinking/brook/releases/download/v${BROOK_VERSION}/brook \
        -O /usr/local/bin/brook \
    && chmod +x /usr/local/bin/brook \
    && ln -sf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone \
    && rm -rf /var/cache/apk/*

CMD ["brook"]
