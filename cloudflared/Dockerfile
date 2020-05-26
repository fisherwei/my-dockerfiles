FROM alpine as base
FROM base as builder

MAINTAINER Fisher Pri Catz "fisher.wei@wqfw.de"

WORKDIR /root

RUN wget https://bin.equinox.io/c/VdrWdbjqyF/cloudflared-stable-linux-amd64.tgz && \
    tar zxvf cloudflared-stable-linux-amd64.tgz && \
    chmod +x cloudflared

ENTRYPOINT ["sh", "-c", "cloudflared tunnel --url $url"]


