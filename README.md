# android_device_xiaomi_apollo
For building TWRP for Xiaomi Mi 10T / 10T Pro / Redmi K30S

*STATUS: TESTING*

 - 对于 红米K30S Ultra 有问题的话联系我。 QQ群：https://jq.qq.com/?_wv=1027&k=L7zFfYra

The Xiaomi Mi 10T serie (codenamed _"apollo"_) are high-end smartphones from Xiaomi.

Xiaomi Mi 10T serie was announced and released in October 2020.


## Device specifications

| Device       | Xiaomi Mi 10T / 10T Pro / Redmi K30S        |
| -----------: | :------------------------------------------ |
| SoC          | Qualcomm SM8250 Snapdragon 865              |
| CPU          | 8x Qualcomm® Kryo™ 585 up to 2.84GHz        |
| GPU          | Adreno 630                                  |
| Memory       | 8GB (LPDDR5)                                |
| Shipped Android version | 10                               |
| Storage      | 128GB / 256GB UFS 3.1 flash storage         |
| Battery      | Non-removable Li-Po 5000mAh                 |
| Dimensions   | 165.1 x 76.4 x 9.3 mm                       |
| Display      | 2400 x 1080 (20:9), 6.67 inch               |

## Features

**Works**

- Booting
- Data decryption
- Vibration
- ADB

**Not Working**

- Adb side load


## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-10.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/apollo" name="Whyle/android_device_xiaomi_apollo" remote="github" revision="android-10.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_apollo-eng
export ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
mka recoveryimage 
```

To test it:

```
fastboot boot out/target/product/apollo/recovery.img
```

## Thanks
- [mauronofrio](https://github.com/mauronofrio)
