FROM python:3.7.10-alpine3.13
LABEL maintainer="Javier Garmon"
ENV PYTHONIOENCODING=UTF-8

ADD entrypoint.sh /entrypoint.sh


RUN apk add --no-cache curl && \
  pip install awscli && \
  curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl && \
  chmod +x ./kubectl && \
  mv ./kubectl /usr/local/bin/kubectl

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
