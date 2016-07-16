FROM ubuntu:wily
MAINTAINER Nicola Kabar <nicolaka@gmail.com>

# Installing some packages
RUN apt-get update -y \
    && apt-get install --no-install-recommends -y \
    build-essential \
    vim \
    git \
    curl \
    python-dev \
    python-pip \ 
    cmake \
    wget \
    sudo \
    iputils-ping \
    ansible \
    ssh \
    && rm -rf /var/lib/apt/lists/*

# Installating Docker Client and Docker Compose

RUN curl -Ssl https://get.docker.com | sh
RUN pip install docker-compose

# Installing + Setting Up GO Environment

ENV GOLANG_VERSION 1.6.2
ENV GOLANG_DOWNLOAD_URL https://golang.org/dl/go$GOLANG_VERSION.linux-amd64.tar.gz
ENV GOLANG_DOWNLOAD_SHA256 e40c36ae71756198478624ed1bb4ce17597b3c19d243f3f0899bb5740d56212a

RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz \
	&& echo "$GOLANG_DOWNLOAD_SHA256  golang.tar.gz" | sha256sum -c - \
	&& sudo tar -C /usr/local -xzf golang.tar.gz \
	&& rm golang.tar.gz

# Setting up GOPATH. For me, i'm using $HOME/code/go
ENV HOME /root
ENV GOPATH $HOME/code/go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

# Setting WORKDIR and USER
USER root
WORKDIR /root

# Sample Bash Profile that will be overwritted if your mounted dir has a .profile
ADD bash_profile  .profile
# Running Bash
CMD ["/bin/bash", "-l"]
