#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

# ImageURL: https://github.com/Azure/azure-functions-docker/blob/master/host/3.0/buster/amd64/java/java8-core-tools.Dockerfile
FROM mcr.microsoft.com/azure-functions/java:3.0-java8-core-tools

RUN mkdir -p /opt/share \
  && wget https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-20.1.0/graalvm-ce-java8-linux-amd64-20.1.0.tar.gz \
  && tar -xvf graalvm-ce-java8-linux-amd64-20.1.0.tar.gz -C /opt/share \
  && rm graalvm-ce-java8-linux-amd64-20.1.0.tar.gz \
  && apt-get update \
  && apt-get install -y gcc \
  && gu install native-image

ENV PATH=/opt/share/graalvm-ce-java8-20.1.0/bin:${PATH} \
  JAVA_HOME=/opt/share/graalvm-ce-java8-20.1.0 \
  XDG_DATA_HOME=/opt/share
