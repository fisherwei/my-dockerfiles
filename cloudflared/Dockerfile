FROM alpine as base
FROM base as builder

MAINTAINER Fisher Pri Catz "fisher.wei@wqfw.de"

WORKDIR /root

COPY cloudflared .

RUN chmod +x cloudflared && \
    mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2

ENTRYPOINT ["sh", "-c", "/root/cloudflared tunnel --url $url"]


