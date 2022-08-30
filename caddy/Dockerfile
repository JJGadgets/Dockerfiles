FROM caddy:2.5.2-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/kirsch33/realip \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2 \
    --with github.com/mholt/caddy-l4 \
    --with github.com/sjtug/caddy2-filter \
    --with github.com/caddyserver/replace-response

FROM caddy:2.5.2

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
