# Venus OS Arm64 Kernel for ESXi-Arm

To boot [Venus OS](https://github.com/victronenergy/venus/wiki) on [ESXi-Arm](https://flings.vmware.com/esxi-arm-edition), a custom Arm64 linux kernel that includes UEFI support must be built and installed to boot Venus OS, which is a 32-Bit OS.

Updated to allow for Remote USB virtualhere.com connection of devices, specifically the Victron Energy VE Connect USB https://www.victronenergy.com/accessories/ve-direct-to-usb-interface

## Prebuilt Kernel Image (Original – Cyprien)

* [Image-Cyprien.gz](https://github.com/Dukat-Gul/venusos-arm64-kernel-for-esxi-arm/blob/master/Image-Cyprien.gz) (MD5: `a06d1e2ac629aff445198a826ef7299a`)

## Prebuilt Kernel Image (Update from above Original /w USBIP and FTDI )

* [Image-Cyprien_Modified_usbip_ftdi.gz]( https://github.com/Dukat-Gul/venusos-arm64-kernel-for-esxi-arm/blob/master/Image-Cyprien_Modified_usbip_ftdi.gz) (MD5: `94a17515098145fabcfb917a8a7ab459`)

## Source
* Arm64 Linux Kernel Source: https://git.kernel.org/torvalds/t/linux-5.14-rc6.tar.gz

## Build (updated – to use either original Cyprien .config or Modified USBIP/FTDI .config)

```bash
cp arch/arm64/configs/defconfig .config && make oldconfig && make Image
```
OR
```bash
cp Cyprien_Modified_usbip_ftdi.config .config && make oldconfig && make Image
```


## Install

* SCP `arch/arm64/boot/Image` to `/u-boot/` directory into Venus OS
