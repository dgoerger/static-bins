FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache git go libc-dev && \
go get -u github.com/juruen/rmapi && \
cd /root && \
go build -ldflags "-linkmode external -extldflags -static" -a github.com/juruen/rmapi && \
strip ./rmapi
