FROM caddy:2.6.2-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2 \
    --with github.com/sjtug/caddy2-filter \
    --with github.com/caddyserver/replace-response

FROM caddy:2.6.2

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
