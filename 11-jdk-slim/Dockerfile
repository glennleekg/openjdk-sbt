FROM openjdk:11-jdk-slim

ENV SBT_VERSION 1.2.8

RUN \
  apt-get update \
  && apt-get install -y apt-transport-https bash curl dirmngr gnupg \
  && echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list \
  && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823 \
  && apt-get update \
  && apt-get install -y sbt \
  && rm -rf /var/lib/apt/lists/*
  
ENV PROJECT_PATH /projects

WORKDIR $PROJECT_PATH

CMD ["bash"]