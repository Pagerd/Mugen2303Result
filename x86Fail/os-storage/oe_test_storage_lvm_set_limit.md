### oe_test_storage_lvm_separate_raid：没有对应模块/没有预装对应软件

riscv对应报错如下

```
spawn lvcreate --type raid10 -i 2 -m 1 -L 50MB --maxrecoveryrate 128 -n test openeulertest
modprobe: FATAL: Module dm-raid not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
y
  /usr/sbin/modprobe failed: 1
  raid10: Required device-mapper target(s) not detected in your kernel.
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

