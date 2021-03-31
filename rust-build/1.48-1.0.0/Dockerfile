FROM rust:1.48-slim

# andreclaudino/rust-build:1.48-1.0.0

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

USER root

RUN apt update && \
    apt install pkg-config build-essential libssl-dev -y && \
    apt-get clean autoclean && \
    apt-get autoremove --yes && \
    rm -rf /var/lib/apt/lists/*