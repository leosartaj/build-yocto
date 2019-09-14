FROM leosartaj/build-yocto-warrior

USER root

WORKDIR /src/poky-warrior

# meta layers for rpi
RUN git clone -b warrior git://git.yoctoproject.org/meta-raspberrypi

WORKDIR /build

COPY ./bblayers.conf.rpi /src

USER yocto
