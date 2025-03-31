FROM alpine:3.21

RUN apk update && \
    apk add mandoc mandoc-apropos mandoc-doc bash bash-doc sudo sudo-doc texlive texlive-full texlive-doc && \
    addgroup -S sudo && \
    echo '%sudo ALL=(ALL:ALL) NOPASSWD:ALL' >> /etc/sudoers

RUN addgroup -g 1000 -S user && \
    adduser -h /home/user -s /bin/bash -G user -S -D -u 1000 user && \
    addgroup user sudo

ENTRYPOINT [ "sleep", "infinity" ]
