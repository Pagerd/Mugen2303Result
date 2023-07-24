### oe_test_storage_lvm_create_snapshot：卷组可用空间不足/没有预装对应软件

riscv对应报错如下

```
+ lvcreate -n test -L 1G -i 1 openeulertest -y
  Volume group "openeulertest" has insufficient free space (124 extents): 256 required.
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

