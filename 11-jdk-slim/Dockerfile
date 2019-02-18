FROM openjdk:11-jdk-slim

RUN \
  apt-get update \
  && apt-get install -y apt-transport-https bash curl dirmngr gnupg \
  && echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list \
  && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823 \
  && apt-get update \
  && apt-get install -y sbt \
  && rm -rf /var/lib/apt/lists/*
  
ARG user=developer
ARG group=developer
ARG home=/home/$user
ARG project=projects/project

RUN \
  groupadd $group \
  && useradd -m -g $group $user

USER $user

RUN mkdir -p $home/$project

WORKDIR $home/$project

CMD ["bash"]