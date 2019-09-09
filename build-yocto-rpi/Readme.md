![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/leosartaj/build-yocto-warrior)

Image for building for rasberry pi using yocto warrior release. Adds meta-raspberrypi layer

### Usage

Build the docker image

```
docker build . -t yocto-rpi
```

Make the local build directory where files will be saved

```
docker volume create --name yoctovol
```

This make sures the filesystem is consistent with
what the container expects for build dir

Run the image.

```
docker run --volume=yoctovol:/build -it yocto-rpi
```

After running, download the source code

Initialize the build environment

```
source /src/poky-warrior/oe-init-build-env /build/build-test
```

This command automatically changes dir to
build directory.

Copy the bblayers.conf.rpi in /src directory.  This adds meta-raspberrpi layer to default bblayers.conf.

```
cp /src/bblayers.conf.rpi /build/build-test/conf/bblayers.conf
```

Edit the ``MACHINE`` variable in conf/local.conf to applicable rpi board. eg. "raspberrypi3"

Run to generate image.

```
bitbake -k core-image-minimal
```

Flash the image on SD card. Boot the pi.
