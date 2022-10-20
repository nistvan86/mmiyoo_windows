# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/rust/.devcontainer/base.Dockerfile

# [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): buster, bullseye
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/rust:0-${VARIANT}

RUN dpkg --add-architecture armhf \
    && apt-get update \
    && apt-get install curl git gcc gcc-arm-linux-gnueabihf -y

RUN bash --login -c "rustup target add armv7-unknown-linux-gnueabihf"

ENV PKG_CONFIG_ALLOW_CROSS=1
ENV CARGO_TARGET_ARMV7_UNKNOWN_LINUX_GNUEABIHF_LINKER=arm-linux-gnueabihf-gcc
ENV CC_armv7_unknown_linux_gnueabihf=arm-linux-gnueabihf-gcc

RUN apt-get install libsdl2-dev libsdl2-dev:armhf -y