FROM caddy:2.9-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/BadAimWeeb/caddy-uwsgi-transport

FROM caddy:2.9-alpine AS base

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
