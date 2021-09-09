## LinkedIn OpenBMC
OpenBMC is an open software framework to build a complete Linux image for a Board Management Controller (BMC). The BMC software for Lightning powershelf and Bolt switch are based on [facebook OpenBMC framework](https://github.com/facebook/openbmc).

### Instructions to build and load BMC firmware

These instructions are only tested with CentOS 7 build environment

##### Getting the source code:
1) mkdir bmc
2) cd bmc
3) git clone -b rocko [https://git.yoctoproject.org/git/poky](https://git.yoctoproject.org/git/poky)
4) cd poky
5) git clone -b rocko  [https://github.com/openembedded/meta-openembedded.git](https://github.com/openembedded/meta-openembedded.git)
6) git clone -b rocko [https://git.yoctoproject.org/git/meta-security](https://git.yoctoproject.org/git/meta-security)
7) git clone https://github.com/truongmd/o19-bmc-firmware.git 

##### Build Delta Power Shelf
From the poky directory:

export TEMPLATECONF=o19-bmc-firmware/meta-openbmc/meta-linkedin/meta-deltapower/conf

source oe-init-build-env

bitbake deltapower-image
