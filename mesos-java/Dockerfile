FROM deepcortex/java-ubuntu:latest

RUN echo "deb http://repos.mesosphere.io/ubuntu/ xenial main" > /etc/apt/sources.list.d/mesosphere.list && \
  apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
  apt-get -y update && \
  apt-get -y install mesos=1.4.1-2.0.1 && \
  apt-get clean && rm -rf /var/lib/apt/lists/*

ENV MESOS_NATIVE_JAVA_LIBRARY=/usr/local/lib/libmesos.so

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
      org.label-schema.docker.cmd="docker run --rm -it deepcortex/mesos-java scala"


