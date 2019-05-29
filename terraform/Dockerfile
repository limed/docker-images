FROM hashicorp/terraform:0.11.14 as terraform
FROM alpine:latest
MAINTAINER "HashiCorp Terraform Team <terraform@hashicorp.com>"

COPY --from=terraform /bin/terraform /bin/terraform

WORKDIR /code

ENTRYPOINT ["/bin/terraform"]
