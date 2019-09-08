FROM leosartaj/build-yocto-warrior

USER root

WORKDIR /src/poky-warrior

# meta layers for rpi
RUN git clone -b warrior git://git.openembedded.org/meta-openembedded
RUN git clone -b warrior https://github.com/meta-qt5/meta-qt5
RUN git clone -b warrior git://git.yoctoproject.org/meta-raspberrypi

WORKDIR /build

USER yocto
