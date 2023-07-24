### oe_test_storage_mount_umount:未知的文件系统类型/没有预装所需软件

riscv的报错log如下

```
+ mount /tmp/data
mount: /tmp/data: unknown filesystem type 'xfs'.
```

而x86没有mkfs，因此配置环境时失败

```
+ mkfs.xfs -f /dev/sr01
oe_test_storage_mount_UUID.sh: line 31: mkfs.xfs: command not found
```

