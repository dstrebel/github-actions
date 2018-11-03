FROM alpine

LABEL maintainer="Dave Strebel <strebeld@gmail.com>"

ARG VCS_REF
ARG BUILD_DATE

LABEL "name"="helm"
LABEL "maintainer"="Dave Strebel <strebeld@gmail.com>"
LABEL "version"="0.9"
LABEL "com.github.actions.icon"="terminal"
LABEL "com.github.actions.color"="black"
LABEL "com.github.actions.name"="helm"
LABEL "com.github.actions.description"="Runs helm client"

ENV HELM_LATEST_VERSION="v2.11.0"

RUN apk add --update ca-certificates \
 && apk add --update -t deps wget \
 && wget https://storage.googleapis.com/kubernetes-helm/helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz \
 && tar -xvf helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz \
 && mv linux-amd64/helm /usr/local/bin \
 && apk del --purge deps \
 && rm /var/cache/apk/* \
 && rm -f /helm-${HELM_LATEST_VERSION}-linux-amd64.tar.gz

ENTRYPOINT ["helm"]
CMD ["help"]