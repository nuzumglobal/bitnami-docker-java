FROM bitnami/oraclelinux-runtimes:7-r286
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages ca-certificates glibc wget zlib
RUN wget -nc -P /tmp/bitnami/pkg/cache/ https://downloads.bitnami.com/files/stacksmith/java-11.0.2-0-linux-x86_64-ol-7.tar.gz && \
    echo "1c363e53c8ffa88cecd893a617c8c614d1418a0c5f44832f60bfd51fceb0095d  /tmp/bitnami/pkg/cache/java-11.0.2-0-linux-x86_64-ol-7.tar.gz" | sha256sum -c - && \
    tar -zxf /tmp/bitnami/pkg/cache/java-11.0.2-0-linux-x86_64-ol-7.tar.gz -P --transform 's|^[^/]*/files|/opt/bitnami|' --wildcards '*/files' && \
    rm -rf /tmp/bitnami/pkg/cache/java-11.0.2-0-linux-x86_64-ol-7.tar.gz

ENV BITNAMI_APP_NAME="java" \
    BITNAMI_IMAGE_VERSION="11.0.2-ol-7-r62" \
    JAVA_HOME="/opt/bitnami/java" \
    PATH="/opt/bitnami/java/bin:$PATH"

CMD [ "bash" ]
