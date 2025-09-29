FROM ubuntu:25.04

RUN mkdir -p /etc/product-service
COPY configs/config-docker.yaml /etc/product-service/config.yaml

RUN useradd -r -u 2000 -s /bin/false product-service && \
    chown -R product-service /etc/product-service

USER product-service

WORKDIR /app

COPY --chown=product-service --chmod=500 product-service ./product-service

ENTRYPOINT ["./product-service", "server"]

