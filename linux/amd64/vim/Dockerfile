FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache binutils gcc git libc-dev make ncurses-dev ncurses-static && \
cd /home && \
git clone https://github.com/vim/vim.git && \
cd /home/vim && \
git checkout v8.2.0000 && \
ln /usr/lib/libncursesw.a /usr/lib/libncurses.a && \
./configure --prefix=/usr --without-x --disable-nls --enable-multibyte --enable-gui=no --with-features=tiny --with-vim-name=vi LDFLAGS='-static' && \
make && \
strip ./src/vi && \
mv ./src/vi /root/vi
