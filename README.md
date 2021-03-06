# Tacx T19xx libusb driver package
This is a [libusb-win32](https://sourceforge.net/projects/libusb-win32/) driver package for the Tacx T1902/T1904/T1932/T1942 head-units. It provides an easy and convenient way to install the drivers necessary to use the Tacx Fortius, Flow and i-Magic trainers with free software like [FortiusANT](https://github.com/WouterJD/FortiusANT) and [GoldenCheetah](https://www.goldencheetah.org) on Windows 7/8/10.

## Installation

1. Download the all-in-one package from https://github.com/switchabl/t19xx_usb/releases/download/v1/libusb-win32_T19xx.exe
2. Run `libusb-win32_T19xx.exe` as Administrator.
3. Click "Next", then "Finish".

## Questions

**Do I need to enable Windows "Test Mode"?**

No. Although the installer package is not signed, the driver itself is. So enabling "Test Mode" is neither necessary nor recommended.

**Do I need to remove the Tacx driver before installing the libusb driver?**

No. The Tacx driver is replaced automatically.

**I have a Tacx Genius/Bushido/Vortex trainer, do I need to install this?**

No, this is only required for USB-connected trainers. The Genius, Bushido and Vortex trainers connect to the PC wirelessly.

**Can I still use TTS4 after installing the libusb drivers?**

You will need to switch back to the Tacx (Jungo) drivers before you can use TTS4 again. The easiest way to do this is to run `TacxDriversSetup.exe` (usually found in `C:\Program Files (x86)\Tacx\TacxTrainersoftware4\TacxDrivers\`).

**I want to install the libusb-win32 drivers manually.**

This driver package is provided merely for convenience. If you wish, you can install the libusb-win32 driver manually, e.g. using [Zadig](https://zadig.akeo.ie/). Note that the T1942 head unit changes its USB ID after the firmware is loaded, so you might have to do this twice.

## Packaging
*Note: This is only necessary if you want to modify or repackage the installer. Normal users can skip this section.*

The driver package is just a standard InfWizard installer with a customized .inf file.

1. Download libusbK from https://sourceforge.net/projects/libusbk/
2. Run InfWizard
3. Choose "libusb0" package
4. Select any device
5. Select "Client installer"
6. Create installer
7. Navigate to the driver package directory
8. Delete the .inf file and replace with `T19xx.inf`
9. Download 7z 9.20 (https://sourceforge.net/projects/sevenzip/files/7-Zip/9.20/7za920.zip/download), newer versions will not work
10. Extract `7za.exe` into driver directory, rename it to `7z.exe`
11. Run `re-pack-files.cmd`
12. `InstallDriver.exe` now contains the T19xx installer.

## License

libusb-win32 is provided under the GNU General Public License version 3. You can find the sources at https://sourceforge.net/projects/libusb-win32/.
