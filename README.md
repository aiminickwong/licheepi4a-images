# LicheePi 4A Images

## Deepin V23

#### Notes

- Rootfs used and from: [*deepin official site (TH1520 Light-a RISC-V)*](https://www.deepin.org/zh/download/), rebuild and add ***revyos*** firmware and kernel modules.
- Boot and U-Boot files used: [***revyos*** **20230511**](https://mirror.iscas.ac.cn/revyos/extra/images/lpi4a/20230511/).
- Support wifi and ethernet.
- Graphics card hardware acceleration has not supported yet (Depends on upstream conditions).
- Default user: **root** and **deepin**, all user's passwords are the same as: **1**.
- You shold resize rootfs with commands:
```
parted -s /dev/mmcblk0 "resizepart 3 -0"
resize2fs /dev/mmcblk0p3
```
- ***Firefox, LibreOffice, Deepin Terminal*** *(Not included by default)*... You can install them by ***apt install pkg_name*** command.
- You can change the dispaly language and set ***Chinese*** input by ***system settings***, default is **English**.
- Deepin RISC-V repos: [mirror.iscas.ac.cn](https://mirror.iscas.ac.cn/deepin-riscv/)
- **Download address 下载地址**: *[Baidu Netdisk]( https://pan.baidu.com/s/1exwIHl16jDHlfPYWWFK8dw?pwd=risc)*

**The 7-zip rootfs image when you have downloaded should be decompressed (下载后的 7-zip rootfs 镜像需要解压缩).**

- How to flash the ***DeepinOS*** image:
```
fastboot.exe flash ram u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe reboot
fastboot.exe flash uboot u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe flash boot boot-20230510-230240.ext4
fastboot.exe flash root rootfs.deepinv23-(08-Nov-2022)-230520-1956.ext4
```
