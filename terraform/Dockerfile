FROM alpine:latest
MAINTAINER "HashiCorp Terraform Team <terraform@hashicorp.com>"

ENV TERRAFORM_VERSION=0.11.14
ENV TERRAFORM_SHA256SUM=829bdba148afbd61eab4aafbc6087838f0333d8876624fe2ebc023920cfc2ad5

RUN apk add --update --no-cache  git curl openssh && \
    curl https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip > terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    echo "${TERRAFORM_SHA256SUM}  terraform_${TERRAFORM_VERSION}_linux_amd64.zip" > terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    sha256sum -cs terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip -d /bin && \
	mkdir -p /code && \
    rm -rf terraform_${TERRAFORM_VERSION}_linux_amd64.zip /var/cache/apk/*

WORKDIR /code

ENTRYPOINT ["/bin/terraform"]
