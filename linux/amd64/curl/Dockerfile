FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc libc-dev make nghttp2-dev nghttp2-static openssl-dev zlib-dev && \
cd /home && \
wget https://curl.haxx.se/download/curl-7.67.0.tar.gz && \
tar -xzf curl-7.67.0.tar.gz && \
cd curl-7.67.0 && \
./configure --with-ca-fallback --with-ca-bundle=/etc/pki/tls/certs/ca-bundle.crt --enable-manual --without-brotli --without-libidn2 --without-libpsl --without-libssh --without-libssh2 --disable-shared LDFLAGS='-static' CFLAGS='-static' CPPFLAGS='-static' LIBS="-ldl" PKG_CONFIG="pkg-config --static" && \
make -j curl_LDFLAGS=-all-static && \
strip ./src/curl && \
mv ./src/curl /root/curl
