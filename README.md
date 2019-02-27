# linux-helios4

Unofficial PKGBUILD for creating an [Arch Linux ARM](https://archlinuxarm.org/) kernel package for the [Helios4](https://kobol.io/helios4/) NAS.

## What is Helios4?

[Helios4](https://kobol.io/helios4/) is an powerful Open Source and Open Hardware Network Attached Storage (NAS) made by Kobol Innovations Pte. Ltd. It harnesses its processing capabilities from the **ARMADA 38x-MicroSoM** from SolidRun, an ARMv7 32-bit SoC.

## Why make a specific Linux package for Helios4? Couldn't I use the official linux-armv7 package?

You could use the official [linux-armv7 PKGBUILD](https://github.com/archlinuxarm/PKGBUILDs/tree/master/core/linux-armv7), but some features could not work as expected.

Actually, the PKGBUILD provided by this repository is based on the linux-armv7 package. It contains the following additional patches which are initially provided by the Kobol Team for Armbian, and are not merged to the upstream kernel yet:

* [91-01-libata-add-ledtrig-support.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-next/91-01-libata-add-ledtrig-support.patch) and [91-02-Enable-ATA-port-LED-trigger.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-next/91-02-Enable-ATA-port-LED-trigger.patch): add support for LED trigger on disk activity
* [92-mvebu-gpio-remove-hardcoded-timer-assignment.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-dev/92-mvebu-gpio-remove-hardcoded-timer-assignment.patch): allows to make the second fan detected by the kernel.
* [94-helios4-dts-add-wake-on-lan-support.patch](https://github.com/armbian/build/blob/master/patch/kernel/mvebu-next/94-helios4-dts-add-wake-on-lan-support.patch): add Wake-on-LAN support for Helios4 (not tested).

Future goal is also to provide a Linux kernel optimizely configured for Helios4.

## Are there prebuilt packages ready to install?

Look at [releases](https://github.com/gbcreation/linux-helios4/releases).

## Known bugs

- ~~LEDs do not light up on disk access.~~ (fixed since 4.20.12-1)

## TODO

- [ ] clean PKGBUILD
- [ ] use a kernel configuration file optimized for Helios4
- [ ] remove useless patches provided by the linux-armv7 PKGBUILD

## Thanks

Thanks to:

- the Kobol Team for this great piece of Open Hardware that is Helios4 NAS
- Aditya from the Kobol Team for his valuable help on explaining various patches and configuration files
- Summers from the Arch Linux ARM forum for his precious advices and encouraging responses

