FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc git libc-dev make && \
git clone https://github.com/ibara/oksh.git /home/oksh && \
cd /home/oksh && \
git checkout oksh-6.7 && \
./configure --enable-ksh --enable-static --prefix=/usr --mandir=/usr/share/man && \
make && \
strip ./ksh && \
mv ./ksh /root/ksh
