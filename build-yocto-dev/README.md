Image for yocto development environment

### Usage

Build the docker image

```
docker build . -t yocto-dev
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

```
git clone git://git.yoctoproject.org/poky
cd /build/poky
```

Checkout the release, eg. morty (yocto 2.2)

```
git checkout -b morty origin/morty
```

Yocto Releases can be checked [here](https://wiki.yoctoproject.org/wiki/Releases)

Initialize the build environment

```
source oe-init-build-env /build/build-test
```

This command automatically changes dir to
build directory.

You can change the configuration in /build/build-test/conf dir

Run to generate image.

```
bitbake -k core-image-minimal
```

### Running the image using qemu

First copy the image to local workspace

You need the container id for doing cp, get this from running container

```
yocto@b1cb86b59e69:/build$
```

Running this in local terminal to copy image,

```
docker cp b1cb86b59e69:/build/build-test/tmp/deploy/images/qemux86 .
```

Now install [qemu](https://en.wikibooks.org/wiki/QEMU/Installing_QEMU).

On Mac run,

```
cd qemux86
qemu-system-i386 -kernel bzImage -hda core-image-minimal-qemux86.ext4 -append "console=ttyS0 root=/dev/hda" -nographic
```

The image boots up

```
Poky (Yocto Project Reference Distro) 2.2.2 qemux86 /dev/tty1

qemux86 login: root
root@qemux86:~# echo hello world
hello world
```
