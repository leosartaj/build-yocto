FROM ubuntu:16.04

RUN apt-get update && apt-get -y upgrade

RUN apt-get install -y gawk wget git-core diffstat unzip texinfo gcc-multilib \
     build-essential chrpath socat libsdl1.2-dev xterm python3 python3-pip

RUN mkdir build

WORKDIR /build
