FROM alpine:3.7

RUN set -ex \
    && apk update \
    && apk add --no-cache \
    tcpdump \
    bridge-utils \
    netcat-openbsd \
    util-linux \ 
    iperf \
    iptables \
    iputils \
    iproute2 \
    iftop \
    drill \
    wireshark \
    nmap
    
CMD ["sh"]


