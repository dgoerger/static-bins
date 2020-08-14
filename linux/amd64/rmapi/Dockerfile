FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils git go libc-dev && \
GO111MODULE=on go get -ldflags "-linkmode external -extldflags '-static -s'" github.com/juruen/rmapi@v0.0.12 && \
mv /root/go/bin/rmapi /root/rmapi
