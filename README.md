# Venus OS Arm64 Kernel for ESXi-Arm

To boot [Venus OS](https://github.com/victronenergy/venus/wiki) on [ESXi-Arm](https://flings.vmware.com/esxi-arm-edition), a custom Arm64 linux kernel that includes UEFI support must be built and installed to boot Venus OS, which is a 32-Bit OS.

## Prebuilt Kernel Image

* [Image.gz](https://github.com/lamw/venusos-arm64-kernel-for-esxi-arm/raw/master/Image.gz) (MD5: `a06d1e2ac629aff445198a826ef7299a`)

## Source
* Arm64 Linux Kernel Source: https://git.kernel.org/torvalds/t/linux-5.14-rc6.tar.gz

## Build

```bash
cp arch/arm64/configs/defconfig .config && make oldconfig && make Image
```

## Install

* SCP `arch/arm64/boot/Image` to `/u-boot/` directory into Venus OS