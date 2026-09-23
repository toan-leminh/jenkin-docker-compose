# Jenkins Dockerfile with Docker CLI installed
# Reference: https://www.jenkins.io/doc/book/installing/docker/
# Reference: https://github.com/vdespa/install-jenkins-docker

FROM jenkins/jenkins:lts-jdk21

USER root

RUN apt-get update && apt-get install -y lsb-release

RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg

RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list

RUN apt-get update && apt-get install -y docker-ce-cli

USER jenkins