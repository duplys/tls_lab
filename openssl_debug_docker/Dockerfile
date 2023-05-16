FROM ubuntu:22.04

RUN apt update && apt install -y \
    gcc \
    gdb \
    libssl-dev \
    make \
    perl \
    vim \
    wget \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /opt/openssl
RUN wget https://www.openssl.org/source/openssl-3.1.0.tar.gz
RUN tar -xvzf openssl-3.1.0.tar.gz 
WORKDIR /opt/openssl/openssl-3.1.0
RUN ./Configure --debug -ggdb -fno-inline && make

ENV LD_LIBRARY_PATH /opt/openssl/openssl-3.1.0:$LD_LIBRARY_PATH

WORKDIR /opt/openssl/openssl-3.1.0

