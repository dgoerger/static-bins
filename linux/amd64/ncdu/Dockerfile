FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc libc-dev make ncurses-dev ncurses-static && \
cd /home && \
wget https://dev.yorhel.nl/download/ncdu-1.14.1.tar.gz && \
tar -xzf ncdu-1.14.1.tar.gz && \
cd ncdu-1.14.1 && \
export LDFLAGS="-static" && \
./configure && \
make && \
strip ./ncdu && \
cp -p ./ncdu /root/ncdu
