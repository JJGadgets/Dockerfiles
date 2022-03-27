FROM caddy:2.5.0-beta.1-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/kirsch33/realip

FROM caddy:2.5.0-beta.1

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
