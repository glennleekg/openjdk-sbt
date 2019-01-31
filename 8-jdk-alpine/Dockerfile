FROM openjdk:8-jdk-alpine

ENV SBT_VERSION 1.2.8

RUN \
  apk add --no-cache bash && \
  apk add --no-cache --virtual=build-dependencies curl gzip && \
  curl -fsSL https://github.com/sbt/sbt/releases/download/v$SBT_VERSION/sbt-$SBT_VERSION.tgz | tar -xzf - -C /usr/local && \
  ln -s /usr/local/sbt/bin/* /usr/local/bin/ && \
  apk del build-dependencies
  
ENV PROJECT_PATH /projects

WORKDIR $PROJECT_PATH

CMD ["bash"]