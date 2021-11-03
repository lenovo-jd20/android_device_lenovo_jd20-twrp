TWRP device tree for Lenovo Z6

The Lenovo Z6 (codenamed _"jd20"_) is a mid-end smartphone from Lenovo.
Lenovo Z6 was announced in July 2019 and released in July 2019.

## Device specifications

Basic   | Spec Sheet
-------:|:-------------------------
SoC     | Qualcomm SDM730 Snapdragon 730
CPU     | Octa-core (2x2.2 GHz Kryo 470 Gold & 6x1.8 GHz Kryo 470 Silver)
GPU     | Adreno 618
Memory  | 6GB / 8GB (LPDDR4X)
Shipped Android Version | 9.0 with ZUI 11
Storage | 64/128 GB UFS2.1
Battery | Non-removable Li-Po 4000 mAh
Display | 1080 x 2340 pixels, 19.5:9 ratio, 162.31 mm (6.39 in), Super AMOLED, HDR10 (~403 ppi density)
Height | 157 mm (6.18 in)
Width | 74.5 mm (2.93 in)
Diameter | 8 mm (0.31 in) 
Weight | 159 g (5.61 oz)
Build | Glass front, glass back, aluminum frame
SIM | Hybrid Dual SIM (Nano-SIM, dual stand-by, dual Volte)
Rear Camera 1 (Sony IMX576) | 24.8MP, f/1.8, 1/2.8 sensor size, PDAF, 0.9µm pixel native / 1.8µm pixels in 6.2MP pixel binning, dual-LED (dual tone) flash
Rear Camera 2 (Samsung s5k5e9) | 5MP, 1/5 sensor size, 1.12um pixel size
Rear Camera 3 (Omnivision 8856) | 8MP, 1/5 sensor size, 1.127 µm pixel size
Front Camera 1 (Samsung S5K3P9) | 16MP, f/2.0, 26mm (wide), 1/3.06 sensor size, 1.0µm pixel size

## Device picture

![Lenovo Z6](https://i.imgur.com/EDdwaj5.jpg)

## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Android Q Support
- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
mkdir -p ~/android/twrp-9.0
cd ~/android/twrp-9.0
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/lenovo/jd20" name="TeamWin/android_device_lenovo_jd20" remote="github" revision="android-9.0" />
```


Finally execute these:

```
. build/envsetup.sh
lunch omni_jd20-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/jd20/recovery.img
```

## Other Sources

Precompiled stock kernel
## Thanks
