FROM ubuntu:16.04

RUN apt-get update && \
    apt-get install -y wget && \
    apt-get install -y openjdk-8-jdk-headless

RUN apt-get install -y ca-certificates-java && \
    update-ca-certificates -f && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/

RUN java -version 2>&1 | grep version | sed -e 's/^openjdk version /JAVA_VERSION=/' > $JAVA_HOME/release

ARG BUILD_DATE=""
ARG VCS_REF=""
ARG IMAGE_VERSION=""

LABEL maintainer="ssemichev@gmail.com" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="DeepCortex" \
      org.label-schema.description="DeepCortex is the world’s first cloud based, automated platform for doing the entire end-to-end Data Science process" \
      org.label-schema.url="http://www.deepcortex.ai" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.version=$IMAGE_VERSION \
      org.label-schema.vcs-url="https://github.com/deepcortex/dockers" \
      org.label-schema.vendor="DeepCortex" \
      org.label-schema.schema-version="1.0" \
      org.label-schema.docker.cmd="docker run --rm -it deepcortex/java-ubuntu /bin/bash"

