FROM golang:alpine
MAINTAINER "HashiCorp Terraform Team <terraform@hashicorp.com>"

LABEL "name"="terraform"
LABEL "version"="0.9"
LABEL "com.github.actions.icon"="terminal"
LABEL "com.github.actions.color"="black"
LABEL "com.github.actions.name"="terraform"
LABEL "com.github.actions.description"="Runs terraform"

ENV TERRAFORM_VERSION=0.10.0

RUN apk add --update git bash openssh

ENV TF_DEV=true
ENV TF_RELEASE=true

WORKDIR $GOPATH/src/github.com/hashicorp/terraform
RUN git clone https://github.com/hashicorp/terraform.git ./ && \
    git checkout v${TERRAFORM_VERSION} && \
    /bin/bash scripts/build.sh

WORKDIR $GOPATH
ENTRYPOINT ["terraform"]