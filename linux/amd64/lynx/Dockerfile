FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc libc-dev make ncurses ncurses-dev ncurses-static libressl-dev zlib-dev zlib-static && \
cd /home && \
wget https://invisible-mirror.net/archives/lynx/tarballs/lynx2.8.9rel.1.tar.gz && \
tar -xzf lynx2.8.9rel.1.tar.gz && \
cd lynx2.8.9rel.1 && \
export CFLAGS="-DNOUSERS" && \
export LDFLAGS="-static -s" && \
export ac_cv_path_BZIP2=none && \
./configure --disable-idna --disable-nls --disable-bibp-urls --disable-dired --disable-finger --enable-ipv6 --enable-widec --with-ssl --with-zlib --without-bzlib --enable-default-colors --with-screen=ncursesw && \
make && \
mv ./lynx /root/lynx
