### oe_test_storage_mount_block_device:Filesystem必须大于300MB/没有预装所需软件

riscv在测试时容量不足

```
+ mkfs.xfs -f /dev/vdb1
Filesystem must be larger than 300MB.
```

而x86没有mkfs，因此配置环境时失败

```
+ mkfs.xfs -f /dev/sr01
oe_test_storage_mount_UUID.sh: line 31: mkfs.xfs: command not found
```

