FROM alpine:3.7
LABEL maintainer="Boris HUISGEN <bhuisgen@hbis.fr>"

ENV S6OVERLAY_VERSION=1.21.4.0 \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=1

RUN apk update && \
    apk upgrade && \
    apk add bash bind-tools ca-certificates curl jq tar && \
    curl -sSL https://github.com/just-containers/s6-overlay/releases/download/v${S6OVERLAY_VERSION}/s6-overlay-amd64.tar.gz | \
        tar xz -C / && \
    apk del tar && \
    rm -rf /var/cache/apk/*

COPY rootfs/ /
