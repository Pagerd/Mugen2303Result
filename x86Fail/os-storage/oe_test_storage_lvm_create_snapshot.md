### oe_test_storage_lvm_create_snapshot：没有对应模块/没有预装对应软件

riscv对应报错如下

```
+ lvcreate -y -L 1G -n original openeulertest
  Volume group "openeulertest" has insufficient free space (124 extents): 256 required.
+ lvcreate --size 100M --snapshot --name snap /dev/openeulertest/original -y
modprobe: FATAL: Module dm-snapshot not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
  /usr/sbin/modprobe failed: 1
  snapshot: Required device-mapper target(s) not detected in your kernel.
  Run `lvcreate --help' for more information.
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

