FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache bearssl-dev binutils gcc libc-dev make perl zlib-dev zlib-static && \
cd /home && \
wget https://curl.haxx.se/download/curl-7.72.0.tar.gz && \
tar -xzf curl-7.72.0.tar.gz && \
cd curl-7.72.0 && \
export LDFLAGS="-static -s" && \
./configure --without-ssl --with-bearssl --disable-debug --disable-curldebug --disable-rt --disable-libtool-lock --enable-http --disable-ftp --disable-file --disable-ldap --disable-ldaps --disable-rtsp --disable-proxy --disable-dict --disable-telnet --disable-tftp --disable-pop3 --disable-imap --disable-smb --disable-smtp --disable-gopher --disable-mqtt --enable-manual --disable-libcurl-option --enable-ipv6 --disable-shared --disable-sspi --disable-crypto-auth --disable-ntlm-wb --disable-tls-srp --disable-unix-sockets --disable-cookies --disable-http-auth --disable-doh --disable-netrc --enable-progress-meter --disable-dnsshuffle --disable-alt-svc --without-zstd --without-libssh2 --without-librtmp --without-libidn2 --without-nghttp2 --without-ngtcp2 --without-nghttp3 --without-quiche --disable-threaded-resolver && \
make LDFLAGS="-static -s -all-static" && \
mv ./src/curl /root/curl
