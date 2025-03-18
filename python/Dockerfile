FROM python:3.12-bookworm

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y vim less sudo && \
    apt-get clean

RUN addgroup --system --gid 1000 user && \
    adduser --system --shell /bin/bash --home /home/user --uid 1000 user && \
    usermod -aG sudo user && \
    sed -i 's/%sudo	ALL=(ALL:ALL) ALL/%sudo	ALL=(ALL:ALL) NOPASSWD:ALL/g' /etc/sudoers

USER user
WORKDIR /home/user

ENTRYPOINT [ "/bin/bash" ]
