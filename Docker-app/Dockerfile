FROM jenkins/jenkins:lts-jdk11

# Switch to root user to install Docker
USER root

# Update apt-get and install Docker and Docker CLI tools
RUN apt-get update \
    && apt-get install -y \
    docker.io \
    docker-ce-cli \
    containerd.io \
    && apt-get clean

# Switch back to the Jenkins user
USER jenkins
