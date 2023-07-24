### oe_test_storage_lvm_cling:内核中没有所需的设备映射器/没有预装对应软件

在riscv中的报错如下

```
spawn lvcreate --type raid1 -m 1 -n test --nosync -L 50MB opentest
modprobe: FATAL: Module dm-raid not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
y
  /usr/sbin/modprobe failed: 1
  raid1: Required device-mapper target(s) not detected in your kernel.
  Run `lvcreate --help' for more information.
+ grep -iE 'error|fail|while executing' testlog
  /usr/sbin/modprobe failed: 1
+ CHECK_RESULT 0 1
+ actual_result=0
+ expect_result=1
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

