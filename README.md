# VoLTE-Fix
Fixes VoLTE in All Mediatek GSI/ROMs

> Important: As Of Now This Fix Only Supports Q Vendor
> Pull Requests are always welcome


Thanks to:

- @phhusson for ims APK build & his GSI's + His Support
- @KhushRajRathod for His Qcom Volte fix Scripts , That helped me alot to make this mtk volte fix
- Ofcourse Me @techyminati xD

# Ways to install

## 1. Using the flashable zip (Simplest)

Go to Releases and download the installer zip.
Then simply flash using any custom recovery such as TWRP/SHRP/PBRP

### Note:

If your Recovery cannot decrypt data, then you need to have root access. Set props manually using

```
setprop persist.dbg.allow_ims_off 1
setprop persist.dbg.volte_avail_ovr 1
setprop persist.dbg.vt_avail_ovr 1
setprop persist.dbg.wfc_avail_ovr 1
setprop persist.sys.phh.ims.caf true
```

**AFTER** booting into system

## 2. Using the Installer Script
> Note: If you're not rooted or are using magisk (that's systemless so it doesn't work), boot into TWRP, and mount system as r/w

Run ``bash ./install.sh`` (uses adb, script needs to be run on a computer)

## 3. Manually
Push the ims folder found inside the 32bit / 64bit folder
> Note: If you're using a version older than AOSP v216, you'll also have to push the android.hardware.telephony.ims.xml to /system/etc/permissions. The script and the zip will automatically add it for you

Set the following properties using setprop

- persist.dbg.allow_ims_off=1
- persist.dbg.volte_avail_ovr=1
- persist.dbg.vt_avail_ovr=1
- persist.dbg.wfc_avail_ovr=1
- persist.sys.phh.ims.caf=true

### For a 64 bit device (arm64)
Copy the 64bit/ims (don't copy the 64bit folder, only the ims folder inside it) folder to /system/priv-app

### For a 32 bit device (arm & a64)
Copy the 32bit/ims (don't copy the 32bit folder, only the ims folder inside it) folder to /system/priv-app

# Ways to uninstall

## 1. Using the Uninstaller Script
> Note: If you're not rooted or are using magisk (that's systemless so it doesn't work), boot into TWRP, and mount system as r/w

Run ``bash ./uninstall.sh``

## 3. Manually
Set the following properties using setprop

- persist.dbg.allow_ims_off to 0
- persist.dbg.volte_avail_ovr to 0
- persist.dbg.vt_avail_ovr to 0
- persist.dbg.wfc_avail_ovr to 0
- persist.sys.phh.ims.caf to false

Remove the ims folder from /system/priv-app/

# For newbies (Some References)

- [What is adb?](https://www.xda-developers.com/what-is-adb/)
- Where should I download adb and fastboot without downloading the entire android sdk? Downloads: [Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip), [macOS](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip), [Linux](https://dl.google.com/android/repository/platform-tools-latest-linux.zip) (These links are maintained by google, you should always get the latest versions)
- How do I download this repository? Use the download button above or just click [here](https://github.com/KhushrajRathod/VoLTE-Fix/archive/master.zip).
