# Magisk Delta

This repo hosts Magisk delta related files

![](https://github.com/topjohnwu/Magisk/raw/master/docs/images/logo.png)

## Introduction

#### **This is not an officially supported [topjohnwu](https://github.com/topjohnwu) project**. 

> If you are looking for official Magisk source, you are in the wrong place, please [go to this page and download Official Magisk](https://github.com/topjohnwu/Magisk)

Yet another crazy custom Magisk by HuskyDG, is always synchronized with official Magisk, including MagiskHide and some custom features.

## Download

> If you are fine with official Magisk setup, it is recommended to stay. If you choose to use Magisk Delta, make sure you read all FAQs and changelog before using Magisk Delta.

### Stable / Beta

> For most user, Stable build is recommended.

#### Stable

- [Magisk 25.2-delta](https://huskydg.github.io/download/magisk/25.2-delta.apk)
- [Source code](https://huskydg.github.io/download/magisk/25.2-delta.zip)
- [Changelog](https://github.com/HuskyDG/magisk-files/blob/main/note_stable.md)

#### Beta

> Currently same as Stable channel


### Canary / Debug

⚠ Magisk Canary/Debug may be unstable and is intended only for advanced users who knew how to recover from a bootloop or crash. 

#### Download

- [Download Canary](https://huskydg.github.io/magisk-files/app-release.apk)
- [Download Debug](https://huskydg.github.io/magisk-files/app-debug.apk)

#### Source code

- [Changelog](https://github.com/HuskyDG/magisk-files/blob/main/note.md)
- [Source code](https://github.com/topjohnwu/Magisk/tree/5dc3b7a6)


## FAQ

### How to switch from current Magisk to Magisk Delta and vice versa?

> Some Mediatek devices prevent boot partition from being modified (or kernel doesn't allow to modify boot image) after booting. When directly installing, you might end up with "/dev/xxxx is read-only" error or the installation seems to be successful but actually fails. In this case, please try patching boot image with Magisk app and flash it from Custom Recovery or Fastboot instead. 

The fast way to migrate to Magisk Delta or switch back to official Magisk: Just flash magisk app like a module.

1. Rename the extension `magisk.apk` to `magisk.zip`
2. Open Magisk app, click "Modules" tab -> "Install from storage" and choose `magisk.zip`
3. Reboot your device


### How to install Magisk into emulator (such as NoxPlayer, LDPlayer, etc...)?

> Currently, only Magisk Delta support Magisk installation into system partition. Although emulator has ramdisk image, patching ramdisk is not used because ramdisk is stored in seperate partition with very SMALL disk size that is not enough to store Magisk binaries.

1. Enable Root access in emulator settings
2. Install and open Magisk Delta
3. Grant root access to Magisk Delta, click "Install" under Magisk field and use "Direct Install into system partition" option instead of "Direct Install" option. If you don't see this option, close and re-open Magisk Delta app.
4. Disable Root access in emulator settings

### Why restore MagiskHide?

MagiskHide is still effectively useful to hide root from almost banking apps and games after it was discontinued by the original developer. 

The reasons why I restore MagiskHide:
- MagiskHide is removed from official Magisk
- [Zygisk is easily detected](#zygisk-is-easily-detected) and there are nearly no complete hiding method for Zygisk.
- The new feature of Magisk called Zygisk is incompatible with Riru

Start with Magisk Delta 25202, to avoid [Tracer detection](https://github.com/vvb2060/magiskdetector), MagiskHide will start to rely on logcat to catch start up app process. For MagiskHide to work, do not disable logd. ROMs with abnormal or slow logcats will cause MagiskHide to work incorrectly. Hiding isolated process and app zygote is now possible in MagiskHide on Android 11 and higher. For Android 10 and bellow, because of isolated processes use the same with zygote's mount namespace, you will need [Riru-Unshare](https://github.com/vvb2060/riru-unshare/releases/latest) to force isolated processes's mount namespace to be detached.

### Why not restore Magisk modules online repo?

The official Magisk modules repository is dead and no longer maintained. Due to that, add them back is meanless. However, [Fox2Code](https://github.com/Fox2Code) has developed [Magisk Modules Manager](https://github.com/Fox2Code/FoxMagiskModuleManager)  app which allows you to download Magisk modules online.

### Zygisk is easily detected

[Read here to learn more about Zygisk...](https://huskydg.github.io/blog/zygisk-can-be-detected-very-easily)

## Other links

- [Internal Documents](./docs/internal-guide.md)

## Other stuff

- [Riru Core](https://github.com/RikkaApps/Riru/releases)
- [Isolated MagiskHider](https://github.com/HuskyDG/riru-momohider/releases)

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
