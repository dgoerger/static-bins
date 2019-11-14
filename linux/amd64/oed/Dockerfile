FROM alpine:latest

RUN echo "nameserver 1.1.1.1" | tee /etc/resolv.conf && \
apk add --no-cache gcc git libc-dev make && \
git clone https://github.com/ibara/oed.git /home/oed && \
cd /home/oed && \
git checkout oed-6.6 && \
./configure --program-name=ed --enable-static && \
echo '#define REG_STARTEND 00004' | tee -a config.h && \
make && \
strip ./ed && \
mv ./ed /root/ed
