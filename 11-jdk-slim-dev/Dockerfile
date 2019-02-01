FROM openjdk:11-jdk-slim

RUN \
  apt-get update \
  && apt-get install -y apt-transport-https bash curl dirmngr gnupg \
  && echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list \
  && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823 \
  && apt-get update \
  && apt-get install -y sbt \
  && rm -rf /var/lib/apt/lists/*
  
RUN \
  curl -sL https://deb.nodesource.com/setup_8.x | bash - \
  && apt-get install -y nodejs git \
  && rm -rf /var/lib/apt/lists/*

ENV PROJECT_PATH /projects

WORKDIR $PROJECT_PATH

CMD ["bash"]