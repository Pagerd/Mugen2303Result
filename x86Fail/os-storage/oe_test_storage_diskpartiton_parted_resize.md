### oe_test_storage_diskpartiton_parted_resize:磁盘标签未识别/未安装预装软件

riscv上有未识别磁盘标签的错误

```
+ parted /dev/vdb
Error: /dev/vdb: unrecognised disk label
Error: /dev/vdb: unrecognised disk label
Error: /dev/vdb: unrecognised disk label
+ grep primary testlog
```

而x86则是不认parted指令

```
+ parted /dev/sr0
oe_test_storage_diskpartiton_parted_resize.sh: line 35: parted: command not found
```

