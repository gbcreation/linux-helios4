# linux-helios4

Unofficial PKGBUILD for creating an [Arch Linux ARM](https://archlinuxarm.org/) kernel package for the [Helios4](https://kobol.io/helios4/) NAS.

## What is Helios4?

[Helios4](https://kobol.io/helios4/) is an powerful Open Source and Open Hardware Network Attached Storage (NAS) made by Kobol Innovations Pte. Ltd. It harnesses its processing capabilities from the **ARMADA 38x-MicroSoM** from SolidRun, an ARMv7 32-bit SoC.

## Why make a specific Linux package for Helios4? Couldn't I use the official linux-armv7 package?

You could use the official [linux-armv7 PKGBUILD](https://github.com/archlinuxarm/PKGBUILDs/tree/master/core/linux-armv7), but some features could not work as expected.

Actually, the PKGBUILD provided by this repository is based on the linux-armv7 package. It contains the following additional patches which are initially provided by the Kobol Team for Armbian, and are not merged to the upstream kernel yet:

* [92-mvebu-gpio-remove-hardcoded-timer-assignment.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-dev/92-mvebu-gpio-remove-hardcoded-timer-assignment.patch): allows to make the second fan detected by the kernel.
* [94-helios4-dts-add-wake-on-lan-support.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-next/94-helios4-dts-add-wake-on-lan-support.patch): add Wake-on-LAN support for Helios4 (not tested).

Future goal is also to provide a Linux kernel optimizely configured for Helios4.

## Are there prebuilt packages ready to install?

Look at [releases](https://github.com/gbcreation/linux-helios4/releases).

## TODO

- [ ] clean PKGBUILD
- [ ] use a kernel configuration file optimized for Helios4
- [ ] remove useless patches provided by the linux-armv7 PKGBUILD

