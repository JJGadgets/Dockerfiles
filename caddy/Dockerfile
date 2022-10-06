FROM caddy:2.6.1-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/kirsch33/realip \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2 \
    --with github.com/mholt/caddy-l4 \
    --with github.com/sjtug/caddy2-filter \
    --with github.com/caddyserver/replace-response
    --with github.com/hslatman/caddy-crowdsec-bouncer/http
    --with github.com/hslatman/caddy-crowdsec-bouncer/layer4

FROM caddy:2.6.1

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
