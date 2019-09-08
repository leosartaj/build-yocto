FROM leosartaj/build-yocto-dev

USER root

WORKDIR /src

RUN git clone -b warrior git://git.yoctoproject.org/poky.git poky-warrior

WORKDIR /build

USER yocto
