### Dockerfile for building latest OpenSSL

# Alpine OS 3.8
# http://dl-cdn.alpinelinux.org/alpine/v3.8/community/x86_64/
FROM bitnami/minideb

RUN set -x \
    && apt-get upgrade \
    && apt-get -y update \
    && apt-get install -y \
		wget \
        build-essential \
        tar \
        perl

COPY . /root/openssl
WORKDIR /root/openssl

RUN set -x \
 && ./Configure linux-x86_64 shared\
 && make -j8 \
 && make install
 
 ENV PATH /usr/local/ssl/bin:$PATH
 