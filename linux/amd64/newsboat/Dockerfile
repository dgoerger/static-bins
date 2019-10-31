FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache asciidoc binutils cargo curl-dev curl-static file g++ gcc gettext-dev gettext-lang gettext-static json-c-dev json-c-static libacl libc-dev libtool libxml2-dev make nghttp2-dev nghttp2-static openssl-dev ncurses-dev ncurses-static sqlite-dev sqlite-static stfl-dev zlib-dev && \
cd /home && \
wget https://newsboat.org/releases/2.17.1/newsboat-2.17.1.tar.xz && \
tar -xJf newsboat-2.17.1.tar.xz && \
cd newsboat-2.17.1 && \
export LDFLAGS="-static -lz -lnghttp2" && \
./config.sh && \
sed -i 's/-L\.\/target\/release/-L\${PWD}\/target\/release/g' Makefile && \
sed -i 's/\$(NEWSBOAT_LIBS)\ \$(LDFLAGS)/-lboat\ -lnewsboat\ -lfilter\ -lpthread\ -lrsspp\ -ldl\ -static\ -L\.\ -lcurl\ -lsqlite3\ -lcurl\ -lxml2\ -lstfl\ -ljson-c\ -lssl\ -lcrypto\ -Wl,--as-needed\ -lncursesw\ -L\/home\/newsboat-2.17.1\/target\/release\ -lz\ -lnghttp2/' Makefile && \
make newsboat && \
strip ./newsboat && \
mv ./newsboat /root/newsboat
