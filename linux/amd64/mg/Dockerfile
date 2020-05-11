FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache gcc git libc-dev make libbsd-dev ncurses-dev ncurses-static && \
git clone https://github.com/ibara/mg.git /home/mg && \
cd /home/mg && \
git checkout 4801f90f47bb165790065823d8ab19c47fa0817b && \
./configure --enable-static --prefix=/usr --mandir=/usr/share/man && \
make && \
strip ./mg && \
mv ./mg /root/mg
