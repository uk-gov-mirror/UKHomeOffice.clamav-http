FROM alpine:3.11

ENV CLAM_VERSION=0.102.4-r0

WORKDIR /clam

RUN apk add --update-cache bash wget shadow \
    clamav=$CLAM_VERSION clamav-libunrar=$CLAM_VERSION

COPY start.sh .

RUN adduser -S -g clamav -u 1000 clam \
    && chown -R clam:clamav /clam /var/log/clamav

USER 1000

EXPOSE 3310
