# oe_test_disk_graphics_card

## 共性的问题

测试套问题，测试依赖 ``lspci`` 命令，这个命令由 pciutils 提供，没有显式安装，且在 x86 和 riscv 镜像中均没有预装

## 不同的问题

grep 结果不符合预期，在 x86 上 ``dmidecode -s bios-version`` 命令输出可能和 qemu 版本有关

在 riscv 和 x86 具有相同的错误输出：

```
+ dmidecode -s bios-version
+ grep -iE '0.0.0|prebuilt.qemu.org'
+ CHECK_RESULT 1
```

以 Archlinux 软件源安装的 qemu 8.0.2 为例，该命令输出如下：

```
# dmidecode -s bios-version

Arch Linux 1.16.2-1-1
```

另外由于 qemu riscv 不使用 bios 启动， ``dmidecode -s bios-version`` 和 ``dmidecode -s bios-vendor`` 输出为空， ``dmidecode`` 命令输出 ``No SMBIOS nor DMI entry point found, sorry.``

