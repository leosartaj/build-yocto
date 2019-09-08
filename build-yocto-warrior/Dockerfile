FROM leosartaj/build-yocto-dev

USER root

WORKDIR /src

RUN wget http://downloads.yoctoproject.org/releases/yocto/yocto-2.7.1/poky-warrior-21.0.1.tar.bz2

RUN tar -xjf poky-warrior-21.0.1.tar.bz2

WORKDIR /build

USER yocto
