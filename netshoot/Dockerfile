FROM alpine:3.4

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
    wireshark 
    
CMD ["sh"]


