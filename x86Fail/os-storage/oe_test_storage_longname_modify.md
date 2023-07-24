### oe_test_storage_longname_modify:没有预装对应软件/指定的不是块设备

riscv没有预装mkfs导致后续测试全部失败

```
+ mkfs.xfs -f /dev/vdd1
oe_test_storage_longname_modify.sh: line 28: mkfs.xfs: command not found
```

x86则是指定了一个错误的块设备

```
+ lsblk --fs /dev/1
+ grep 1
lsblk: /dev/1: not a block device
+ CHECK_RESULT 1 0 0 'Failed to view file system type'
```

