### oe_test_storage_diskpartiton_fdisk_settype:没有预装对应软件

riscv上报错如下所示

```
+ fdisk /dev/vdb
+ echo -e 'print\ntype\n2\nL\n1\nw\n'
L: unknown command
1: unknown command
+ partprobe
```

而x86额外显示找不到此介质

```
+ fdisk /dev/sr0
fdisk: cannot open /dev/sr0: No medium found
+ partprobe
oe_test_storage_diskpartiton_fdisk_settype.sh: line 37: partprobe: command not found
+ CHECK_RESULT 127
+ actual_result=127
```

