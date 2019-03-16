FROM alpine as base
FROM base as builder

MAINTAINER Fisher Pri Catz "fisher.wei@wqfw.de"

WORKDIR /backup

ENTRYPOINT ["sh", "-c", "tar czf /backup/$(date +'%Y%m%d_%H%M%S').tar.gz $TARGET"]


