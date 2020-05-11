FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc git libc-dev make && \
git clone https://github.com/gavinhoward/bc.git /home/bc && \
cd /home/bc && \
git checkout 2.7.2 && \
export LDFLAGS='-static' && \
./configure.sh --disable-prompt --bc-only --disable-history && \
make && \
mv ./bin/bc /root/bc
