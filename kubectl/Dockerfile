FROM alpine:3.8

LABEL "name"="kubectl"
LABEL "maintainer"="strebeld@gmail.com"
LABEL "version"="0.9"
LABEL "com.github.actions.icon"="terminal"
LABEL "com.github.actions.color"="black"
LABEL "com.github.actions.name"="kubectl"
LABEL "com.github.actions.description"="Runs Kubectl"

ENV KUBECTL_VERSION="v1.11.4"

RUN apk add --no-cache ca-certificates bash git curl && wget -q https://storage.googleapis.com/kubernetes-release/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -O /usr/local/bin/kubectl && chmod +x /usr/local/bin/kubectl

CMD sh