### oe_test_storage_ext4_mount_write：测试文件不存在

riscv与x86报错内容相同

报错内容如下

```
+ mkfs.ext4 -F /dev/sr01
mke2fs 1.46.5 (30-Dec-2021)
The file /dev/sr01 does not exist and no size was specified.
```

同时x86的LOG_INFO打错了

```
+ LOGi_INFO 'Environmental preparation is over.'
oe_test_storage_ext4_mount_write.sh: line 25: LOGi_INFO: command not found
```

