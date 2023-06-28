FROM ubuntu:22.04

RUN apt update && apt install -y \
    gcc \
    make \
    perl \
    wget \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /opt/openssl
RUN wget https://www.openssl.org/source/openssl-1.1.1f.tar.gz
RUN tar -xvzf openssl-1.1.1f.tar.gz 
WORKDIR /opt/openssl/openssl-1.1.1f
RUN ./config && make && make install
RUN export LD_LIBRARY_PATH=/opt/openssl/openssl-1.1.1f:$LD_LIBRARY_PATH

WORKDIR /opt/openssl
