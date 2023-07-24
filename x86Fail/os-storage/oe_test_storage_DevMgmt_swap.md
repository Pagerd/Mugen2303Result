### oe_test_storage_DevMgmt_swap：软件套部分编写错误，没有对应的预装软件

riscv与x86有相同的报错

```
+ swapon /dev/mapper/
swapon: /dev/mapper: insecure permissions 0755, 0600 suggested.
swapon: /dev/mapper: read swap header failed
+ swapoff -v /dev/mapper/
swapoff: /dev/mapper/: swapoff failed: Is a directory
swapoff /dev/mapper/
```

同时x86上有部分指令没有预先安装软件

```
+ lvresize -f /dev//swap -L -100M
oe_test_storage_DevMgmt_swap.sh: line 48: lvresize: command not found
```

而riscv在这部分的报错为

```
Fri Apr 28 07:07:52 2023 - ERROR - oe_test_storage_DevMgmt_swap.sh line 47
+ '[' 0 -eq 1 ']'
+ return 0
+ lvresize -f /dev//swap -L -100M
  Volume group "swap" not found
  Cannot process volume group swap
+ CHECK_RESULT 5
```

