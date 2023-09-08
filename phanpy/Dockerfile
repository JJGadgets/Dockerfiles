FROM docker.io/node:20 AS builder
RUN git clone --depth 1 --branch production https://github.com/cheeaun/phanpy.git /app
WORKDIR /app

RUN npm install
RUN npm run build

FROM public.ecr.aws/docker/library/caddy:2.7.4 AS caddy

FROM gcr.io/distroless/static-debian12:nonroot
COPY --from=builder /app/dist /app
COPY --from=caddy /usr/bin/caddy /caddy
WORKDIR /app
ENTRYPOINT ["/caddy", "file-server", "--root", "/app", "--listen", ":8080"]

LABEL org.opencontainers.image.source=https://github.com/JJGadgets/Dockerfiles
