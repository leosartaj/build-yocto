Image for yocto development environment

### Usage

Build the docker image

``docker build . -t yocto-dev``

Make the build directory

``mkdir build``

Run the image.

``docker run --volume=${PWD}/build:/build -it yocto-dev``

After running, download the source code

``git clone git://git.yoctoproject.org/poky``

``cd /build/poky``

Checkout the release, here we checkout warrior (yocto 2.1)
``git checkout -b krogoth origin/krogoth``

Yocto Releases can be checked [here](https://wiki.yoctoproject.org/wiki/Releases)

Initialize the build environment

``source oe-init-build-env /build/build-test``

This command automatically changes dir to
build directory.

You can change the configuration in /build/build-test/conf dir

Run to generate image.

``bitbake -k core-image-minimal``
