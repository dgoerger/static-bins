FROM golang:alpine

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils git libc-dev && \
go get -u github.com/tealeg/xlsx2csv && \
cd /root && \
go build -a github.com/tealeg/xlsx2csv && \
strip ./xlsx2csv
