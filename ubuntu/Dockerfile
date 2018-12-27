FROM ubuntu:18.04

RUN apt-get update \
    && apt-get -y install apt-transport-https ca-certificates curl make software-properties-common \
    && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - \
    && apt-key fingerprint 0EBFCD88 \
    && add-apt-repository \
       "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
       $(lsb_release -cs) \
       stable" \
    && apt-get -y install docker-ce

RUN curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose \
    && chmod +x /usr/local/bin/docker-compose \
    && docker-compose --version

RUN apt-get update \
    && apt-get -y install gcc

RUN apt-get update \
    && apt-get -y install wget

# Install go

RUN wget https://dl.google.com/go/go1.10.linux-amd64.tar.gz \
    && tar -xvf go1.10.linux-amd64.tar.gz \
    && mv go /opt \
    && export GOROOT=/opt/go \
    && export GOPATH=$HOME/Projects/Golang \
    && export PATH=$GOPATH/bin:$GOROOT/bin:$PATH \
    && go version \
    && go env
