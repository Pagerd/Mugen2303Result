### oe_test_storage_lvm_create_raid：没有对应模块/没有预装对应软件

riscv对应报错如下

```
+ vgcreate openeulertest /dev/vdb /dev/
  No device found for /dev/.
  Command requires all devices to be found.
+ grep 'VG Name'
+ vgdisplay
+ grep openeulertest
+ CHECK_RESULT 1
```

而x86没有预装对应软件 因此测试失败

```
+ pvcreate -y /dev/vdd
oe_test_storage_lvm_cling.sh: line 23: pvcreate: command not found
+ vgcreate opentest /dev/vdd
oe_test_storage_lvm_cling.sh: line 24: vgcreate: command not found
+ vgextend opentest /dev/sr0 /dev/vdb /dev/vdc -y
oe_test_storage_lvm_cling.sh: line 25: vgextend: command not found
```

