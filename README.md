# Magisk 32-bit and Magisk Delta 32-bit

This repository hosts the application files for Magisk 32-bit and Magisk Delta 32-bit, which allow usage of 32-bit applications on the Pixel 7 line of phones.

## Introduction

#### **This is not officially endorsed by either topjohnwu or HuskyDG, any issues resulting from the project are to be directed towards the repository owner**

> If you are looking for official Magisk source, you are in the wrong place, please [go to this page and download Official Magisk](https://github.com/topjohnwu/Magisk)

Custom forks of Magisk and Magisk Delta, Magisk 32-bit and Magisk Delta 32-bit enable the usage of 32-bit applications on the Pixel 7 by starting the secondary Zygote process.

There are two 'flavors' available:
 
  - Magisk 32-bit
  - Magisk Delta 32-bit
  
Both 'flavors' allow for the installation and execution of 32-bit applications, however there is a difference in featureset between them.

### Magisk 32-bit
Is essentially stock [Magisk](https://github.com/topjohnwu/Magisk) with the addition of overriding the vendor build.prop to enable the secondary Zygote process.

It is the recommended 'flavor' to run.

### Magisk Delta 32-bit
Is an enhanced Magisk fork by [HuskyDG](https://github.com/HuskyDG/Magisk/tree/delta) that has additional features power-users may find helpful.

The additional features are, and not limited to as more are added:
- early-mount.d: Mount files before the init process is ran
- init.rc injection: Inject rc scripts without having to rebuild the initrd
- Systemless file removal: Remove file and folders systemlessly
- SuList: Hides Magisk binaries by default and only whitelisted processes can use Magisk
- Maru: Zygisk implementation using Native Bridge

It is not recommended to run Magisk Delta 32-bit as these features are positioned for power-users and I only offer Magisk Delta 32-bit _as-is_ as I do not daily it.

## Download

> If you are fine with a stock Magisk setup, then it is recommended to stay on it. Part of the installation steps requires wiping your device, so backup your data before doing so. If you choose to use Magisk Delta 32-bit, make sure you read all FAQs and documentation from the [Magisk Delta repository](https://github.com/HuskyDG/magisk-files/tree/main) before using Magisk Delta 32-bit.

#### Download Links

- [Download Magisk 32-bit](https://raw.githubusercontent.com/Namelesswonder/magisk-files/main/magisk-32bit-release.apk)

- [Download Magisk Delta 32-bit](https://raw.githubusercontent.com/Namelesswonder/magisk-files/main/magisk-delta-32bit-release.apk)

- [Combined changelog](https://github.com/Namelesswonder/magisk-files/blob/main/changelog.md)

- [Magisk Delta documentation](https://github.com/HuskyDG/magisk-files/tree/main)

#### Debug Releases

> If you have issues with the forks then it would be helpful to install the debug builds and grab logs

- [Download Magisk 32-bit Debug](https://raw.githubusercontent.com/Namelesswonder/magisk-files/main/magisk-32bit-debug.apk)

- [Download Magisk Delta 32-bit Debug](https://raw.githubusercontent.com/Namelesswonder/magisk-files/main/magisk-delta-32bit-debug.apk)

## Installation

**It is best to follow the steps from the [XDA thread](https://forum.xda-developers.com/t/4521029)**

### Magisk 32-bit

1. Delete old Magisk app (if it is installed)
2. Install Magisk 32-bit APK
3. Copy stock `init_boot.img` over to device
4. Patch stock `init_boot.img` with the app
5. Copy patched `magisk_*.img` over to computer
6. Flash patched `magisk_*.img` to device
7. Wipe data with `fastboot -w`
8. Reinstall Magisk 32-bit APK when done with device setup

### Magisk Delta 32-bit

__If you are not already rooted then you can backup your persist partition after installing Magisk Delta 32-bit__

1. Backup persist partition by running the following command as root `dd if=/dev/block/by-name/persist of=/sdcard/persist-backup.img`
2. Copy backed up persist image to computer
3. Delete old Magisk app (if it is installed)
4. Install Magisk Delta 32-bit APK
5. Copy stock `init_boot.img` over to device
6. Patch stock `init_boot.img` with the app
7. Copy patched `magisk_*.img` over to computer
8. Flash patched `magisk_*.img` to device
9. Wipe data with `fastboot -w`
10. Reinstall Magisk Delta 32-bit APK when done with device setup

## Updating

### Magisk 32-bit

__Once I get the JSON files setup (soon) the update process will be easier__

1. Restore Magisk 32-bit app if it has been hidden
2. Install new Magisk 32-bit APK
3. Copy stock `init_boot.img` over to device
4. Patch stock `init_boot.img` with the app
5. Copy patched `magisk_*.img` over to computer
6. Flash patched `magisk_*.img` to device

### Magisk Delta 32-bit

__Once I get the JSON files setup (soon) the update process will be easier__

1. Restore custom Magisk Delta app if it has been hidden
2. Install new Magisk Delta 32-bit APK
3. Copy stock `init_boot.img` over to device
4. Patch stock `init_boot.img` with the app
5. Copy patched `magisk_*.img` over to computer
6. Flash patched `magisk_*.img` to device

## Uninstallation

### Magisk 32-bit

1. Remove all Magisk modules from app
2. Click "Uninstall Magisk" inside the app
3. Reboot device to bootloader
4. Flash the stock `init_boot.img` to device

### Magisk Delta 32-bit

1. Remove all Magisk modules from app
2. Click "Uninstall Magisk" inside the app
3. Reboot device to bootloader
4. Flash the stock `init_boot.img` to device
5. Flash the backed up persist `fastboot flash persist persist-backup.img`

## SafetyNet

This modification should not have any bearing on your ability to pass SafetyNet, so are you still at the whim the cat-and-mouse game.

## Credits

- Magisk Delta author: [HuskyDG](https://github.com/HuskyDG)
- Magisk author: [topjohnwu](https://github.com/topjohnwu/magisk)
- Magisk contributors: [vvb2060](https://github.com/vvb2060), [yujincheng08](https://github.com/yujincheng08), [RikkaW](https://github.com/RikkaW), [canyie](https://github.com/canyie)
- Maru (zygisk native bridge): [5ec1cff](https://github.com/5ec1cff)
- Other: [osm0sis](https://github.com/osm0sis), [diareuse](https://github.com/diareuse),...

## License

Our license obviously is the same as [Magisk's license](https://github.com/topjohnwu/Magisk#License)

```
Magisk, including all git submodules are free software:
you can redistribute it and/or modify it under the terms of the
GNU General Public License as published by the Free Software Foundation,
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```
