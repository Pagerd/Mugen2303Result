### oe_test_MEMinfo_001

x86_64和risc-v两种架构下`lshw -c memory `命令的输出格式不一样，x86_64:

```
[root@localhost ~]# lshw -c memory
  *-firmware
       description: BIOS
       vendor: SeaBIOS
       physical id: 0
       version: rel-1.16.2-0-gea1b7a073390-prebuilt.qemu.org
       date: 04/01/2014
       size: 96KiB
  *-memory
       description: System Memory
       physical id: 1000
       size: 8GiB
       capabilities: ecc
       configuration: errordetection=multi-bit-ecc
     *-bank
          description: DIMM RAM
          vendor: QEMU
          physical id: 0
          slot: DIMM 0
          size: 8GiB
```



risc-v:

```
[root@openeuler-riscv64 oe_test_iscsi]# lshw -c memory
  *-memory
       description: System memory
       physical id: 9
       size: 3938MiB
```



测试机脚本中查找的字段在risc-v中没有。