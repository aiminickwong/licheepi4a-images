# LicheePi 4A Images

- **1.[DeepinOS V23](./#1deepinos-v23)**
- **2.[openKylin v0.9.5](./#2openkylin-v095)**

----

## 1.DeepinOS V23

#### Notes

- Rootfs (with ***DDE*** desktop) used and from: [*deepin official site (TH1520 Light-a RISC-V)*](https://www.deepin.org/zh/download/), rebuild and add ***revyos*** firmware and kernel modules.
- Boot and U-Boot files used: [***revyos*** **20230511**](https://mirror.iscas.ac.cn/revyos/extra/images/lpi4a/20230511/).
- Support wifi and ethernet.
- Graphics card hardware acceleration has not supported yet (Depends on upstream conditions).
- Default user: **root** and **deepin**, all user's passwords are the same as: **1**.
- You shold resize rootfs with commands:
```
sudo parted -s /dev/mmcblk0 "resizepart 3 -0"
sudo resize2fs /dev/mmcblk0p3
```
- ***Firefox, LibreOffice, Deepin Terminal*** *(Not included by default)*... You can install them by ***apt install pkg_name*** command.
- You can change the dispaly language and set ***Chinese*** input by ***system settings***, default is **English**.
- Deepin RISC-V repos: [mirror.iscas.ac.cn](https://mirror.iscas.ac.cn/deepin-riscv/)
```
deb [trusted=yes] https://mirror.iscas.ac.cn/deepin-riscv/deepin-stage1/ beige main 
deb [trusted=yes] https://mirror.iscas.ac.cn/deepin-riscv/deepin-addons/ beige main
```
- **Download link 下载链接**: *[Baidu Netdisk](https://pan.baidu.com/s/1exwIHl16jDHlfPYWWFK8dw?pwd=risc)*

**The 7-zip rootfs image when you have downloaded should be decompressed.**

**下载后的 7-zip rootfs 镜像需要解压缩.**

- How to flash the ***DeepinOS*** image:
```
fastboot.exe flash ram u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe reboot
fastboot.exe flash uboot u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe flash boot boot-20230510-230240.ext4
fastboot.exe flash root rootfs.deepinv23-(08-Nov-2022)-230520-1956.ext4
```

----

## 2.openKylin v0.9.5

#### Notes

- Rootfs (with ***UKUI*** desktop) used and from: [*openkylin official site (Thead1520)*](https://www.openkylin.top/downloads/index-cn.html), resize rootfs image, rebuild and add ***revyos*** firmware and kernel modules.
- Boot and U-Boot files used: [***revyos*** **20230511**](https://mirror.iscas.ac.cn/revyos/extra/images/lpi4a/20230511/).
- Support wifi and ethernet.
- Graphics card hardware acceleration has not supported yet (Depends on upstream conditions).
- Default user: **openkylin**, password: **openkylin**.
- You shold resize rootfs with commands:
```
sudo parted -s /dev/mmcblk0 "resizepart 3 -0"
sudo resize2fs /dev/mmcblk0p3
```
- The default language is ***Chinese***.
- openKylin RISC-V repos: [archive.build.openkylin.top](http://archive.build.openkylin.top/openkylin/)
```
deb http://archive.build.openkylin.top/openkylin/ yangtze main cross pty
deb http://archive.build.openkylin.top/openkylin/ yangtze-security main cross pty
deb http://archive.build.openkylin.top/openkylin/ yangtze-updates main cross pty
deb http://archive.build.openkylin.top/openkylin/ yangtze-proposed main cross pty
```
- **Download link 下载链接**: *[Baidu Netdisk](https://pan.baidu.com/s/1XT-u7zeom3vP_8ybcC_Mvw?pwd=risc)*

**The 7-zip rootfs image when you have downloaded should be decompressed.**

**下载后的 7-zip rootfs 镜像需要解压缩.**

- How to flash the ***openKylin*** image:
```
fastboot.exe flash ram u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe reboot
fastboot.exe flash uboot u-boot-with-spl-lpi4a-20230510.bin
fastboot.exe flash boot boot-20230510-230240.ext4
fastboot.exe flash root openkylin-0.9.5-thead1520-230521.ext4
```
#### Issues
- ***kylin-virtual-keyboard*** and ***ukui-sidebar*** used high cpu usage.

remove them:
```
sudo rm -f /etc/xdg/autostart/kylin-virtual-keyboard.desktop
sudo rm -f /etc/xdg/autostart/ukui-sidebar.desktop
sudo reboot
```
For more less cpu usage, you can remove more autostart apps, for example:
```
sudo rm -f /etc/xdg/autostart/ukui-search* \
/etc/xdg/autostart/ukui-tablet-desktop.desktop \
/etc/xdg/autostart/ukui-volume-control-applet.desktop
```

