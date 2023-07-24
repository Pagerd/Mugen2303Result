### oe_test_storage_mount_UUID:无法找到UUID 1/没有预装所需软件

riscv在挂载UUID=1.0的数据时出错

```
mount: /tmp/data: can't find UUID=1.0.
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

而x86没有mkfs，因此配置环境时失败

```
+ mkfs.xfs -f /dev/sr01
oe_test_storage_mount_UUID.sh: line 31: mkfs.xfs: command not found
```

