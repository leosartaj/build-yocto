Image for yocto development environment

### Usage

Build the docker image

``docker build . -t yocto-dev``

Make the build directory

``mkdir build``

Run the image.

``docker run . --volume=${PWD}/build:/home/build -it yocto-dev bash``

After running, download the source code

``git clone git://git.yoctoproject.org/poky``
