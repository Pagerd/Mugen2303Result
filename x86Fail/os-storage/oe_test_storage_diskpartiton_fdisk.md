### oe_test_storage_diskpartiton_fdisk:值超出范围/找不到此介质

riscv上报错如下所示

```
+ fdisk /dev/vdb
Value out of range.
```

而x86则显示找不到此介质

```
+ fdisk /dev/sr0
fdisk: cannot open /dev/sr0: No medium found
```

