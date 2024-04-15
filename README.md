# Build instructions
source poky/oe-init-build-env rpi-build

copy conf directory to rpi-build/conf
bitbake -c cleanall core-image-base
bitbake core-image-base

# Important changes
Following changes to be noted in local.conf file

LICENSE_FLAGS_ACCEPTED += “synaptics-killswitch”
IMAGE_FSTYPES="rpi-sdimg”

# Flash image
Final image is created at rpi-build/tmp/deploy/images/raspberrypi3/core-image-base-raspberrypi3.rootfs-20240415080533.rootfs.rpi-sdimg

Use https://etcher.balena.io/ to flash the image on SD card.
