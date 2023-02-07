FROM alpine:latest

RUN apk update \
    && apk upgrade \
    && apk add curl \
    && apk add unzip

RUN curl -LO https://releases.hashicorp.com/vault/1.12.0/vault_1.12.0_linux_amd64.zip \
    && unzip *.zip \
    && rm -r *.zip \
    && chmod +x vault \
    && mv vault /usr/local/bin

ENV VAULT_ADDR 'http://127.0.0.1:8200'

ENTRYPOINT [ "sh", "-c", "vault server -dev" ]

EXPOSE 8200
