### oe_test_storage_mount_mobile_point:目标不是块设备/没有预装所需软件

riscv在使用mount命令时出错

```
+ mount /dev/ /mnt
mount: /mnt: /dev is not a block device.
+ CHECL_RESULT 32
oe_test_storage_mount_mobile_point.sh: line 34: CHECL_RESULT: command not found
+ mount --make-private /mnt
mount: /mnt: not mount point or bad option.
```

值得一提的是这里check result写错了，因此也报错

```
+ CHECL_RESULT 32
oe_test_storage_mount_mobile_point.sh: line 34: CHECL_RESULT: command not found
```

而x86没有mkfs，因此配置环境时失败

```
+ mkfs.xfs -f /dev/sr01
oe_test_storage_mount_UUID.sh: line 31: mkfs.xfs: command not found
```

