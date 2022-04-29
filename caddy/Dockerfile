FROM caddy:2.5.0-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/kirsch33/realip \
    --with github.com/lucaslorentz/caddy-docker-proxy \
    --with github.com/mholt/caddy-l4 \
    --with github.com/sjtug/caddy2-filter

FROM caddy:2.5.0

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
