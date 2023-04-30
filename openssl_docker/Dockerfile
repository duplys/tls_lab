FROM ubuntu:22.04

RUN apt update && apt install -y \
    gcc \
    make \
    perl \
    wget \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /opt/openssl
RUN wget https://www.openssl.org/source/openssl-3.1.0.tar.gz
RUN tar -xvzf openssl-3.1.0.tar.gz 
WORKDIR /opt/openssl/openssl-3.1.0
RUN ./Configure && make && make test && make install

WORKDIR /opt/openssl
