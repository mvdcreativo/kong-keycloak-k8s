FROM kong:2.8.1
USER root
RUN apk add --no-cache git unzip luarocks && \
    luarocks install kong-oidc
USER kong