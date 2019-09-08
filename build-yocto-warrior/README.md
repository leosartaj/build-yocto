Image for yocto development environment with warrior release

### Usage

Build the docker image

```
docker build . -t yocto-warrior
```

Make the local build directory where files will be saved

```
docker volume create --name yocotvol
```

This make sures the filesystem is consistent with
what the container expects for build dir

Run the image.

```
docker run --volume=yoctovol:/build -it yocto-dev
```

After running, download the source code

Initialize the build environment

```
source /src/poky-warrior/oe-init-build-env /build/build-test
```

This command automatically changes dir to
build directory.

You can change the configuration in /build/build-test/conf dir

Run to generate image.

```
bitbake -k core-image-minimal
```

For running the image using qemu refer the instructions [here](build-yocto-dev#running-the-image-using-qemu)
