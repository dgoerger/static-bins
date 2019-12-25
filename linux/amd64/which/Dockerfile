FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc libc-dev make && \
cd /home && \
wget https://carlowood.github.io/which/which-2.21.tar.gz && \
tar -xzf which-2.21.tar.gz && \
cd /home/which-2.21 && \
./configure --disable-iberty LDFLAGS='-static' && \
make && \
strip ./which && \
mv ./which /root/which
