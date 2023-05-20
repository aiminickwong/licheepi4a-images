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
- **Download address**: *[Baidu Netdisk]*( https://pan.baidu.com/s/1exwIHl16jDHlfPYWWFK8dw?pwd=risc)
