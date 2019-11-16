FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache gcc libc-dev libevent-dev libevent-static make ncurses-dev ncurses-static && \
cd /home && \
wget https://github.com/tmux/tmux/releases/download/2.9/tmux-2.9.tar.gz && \
tar -xzf tmux-2.9.tar.gz && \
cd /home/tmux-2.9 && \
./configure --enable-static --prefix=/usr LDFLAGS='-static' && \
make && \
strip ./tmux && \
mv ./tmux /root/tmux
