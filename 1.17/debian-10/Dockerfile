FROM docker.io/bitnami/minideb:buster
LABEL maintainer "Mikhail <mikkra@xaked.com>"

ENV HOME="/" \
    OS_ARCH="amd64" \
    OS_FLAVOUR="debian-10" \
    OS_NAME="linux"

COPY prebuildfs /
# Install required system packages and dependencies
RUN install_packages ca-certificates curl gzip procps tar wget
RUN wget -nc -P /tmp/mikkra/pkg/cache/ https://downloads.bitnami.com/files/stacksmith/kubectl-1.17.9-0-linux-amd64-debian-10.tar.gz && \
    echo "155e1c44834f597b2543bc2929f534c80483653fc7baac16eba29968979e6b0b  /tmp/mikkra/pkg/cache/kubectl-1.17.9-0-linux-amd64-debian-10.tar.gz" | sha256sum -c - && \
    tar -zxf /tmp/mikkra/pkg/cache/kubectl-1.17.9-0-linux-amd64-debian-10.tar.gz -P --transform 's|^[^/]*/files|/opt/mikkra|' --wildcards '*/files' && \
    rm -rf /tmp/mikkra/pkg/cache/kubectl-1.17.9-0-linux-amd64-debian-10.tar.gz
RUN apt-get update && apt-get upgrade -y && \
    rm -r /var/lib/apt/lists /var/cache/apt/archives
RUN chmod g+rwX /opt/mikkra

ENV PATH="/opt/mikkra/kubectl/bin:$PATH"

USER 1001
ENTRYPOINT [ "kubectl" ]
CMD [ "--help" ]
