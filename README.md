# U-boot bootloader for reMarkable Paper Pro

This repository provides buildable kernel source tree snapshots based on the reMarkable software version.
The source code is stored using git lfs. You might need to run `git lfs install` depending on your system.

> [!WARNING]
> Due to secure boot on the reMarkable Paper Pro device the compiled U-boot binary will not be able to run
> without being signed with the reMarkable private signing key.

# Build instructions (example)
```shell
git clone git@github.com:reMarkable/uboot-imx.git && cd uboot-imx-rm
git checkout rmpp_2023.04_v3.14.x

tar xzvf uboot-imx-rel-4.0-jv-3.14.1.10-4929b535df.tar.gz
cd uboot-imx-rel-4.0-jv-3.14.1.10-4929b535df

export make=make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu-
make ferrari_defconfig
make -j$(nproc)
```
