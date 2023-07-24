### oe_test_storage_mount_findmnt:无法找到mnt/没有预装所需软件

riscv在使用mnt命令时出错

```
+ findmnt
+ grep /tmp/data_xfs
+ CHECK_RESULT 1
```

而x86没有mkfs，因此配置环境时失败

```
+ mkfs.xfs -f /dev/sr01
oe_test_storage_mount_UUID.sh: line 31: mkfs.xfs: command not found
```

