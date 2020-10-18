FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc libc-dev make && \
wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-3.1.4.tar.gz && \
tar -xzf libressl-3.1.4.tar.gz && \
cd libressl-3.1.4 && \
./configure --prefix=/ && \
make LDFLAGS='-all-static -s' && \
mv ./apps/openssl/openssl /root/openssl && \
mv ./apps/nc/nc /root/nc
