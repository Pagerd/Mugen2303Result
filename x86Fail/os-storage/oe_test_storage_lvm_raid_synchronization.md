### oe_test_storage_lvm_raid_synchronization：没有对应模块/没有预装对应软件

riscv对应报错如下

```
+ expect -c '
    set timeout 30
    log_file testlog
    spawn lvcreate --type raid1 -m 1 -L 1G -n test openeulertest -y
    expect "*\[y/n\]*" {send "y\r"}
    expect eof
'
spawn lvcreate --type raid1 -m 1 -L 1G -n test openeulertest -y
modprobe: FATAL: Module dm-raid not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
  /usr/sbin/modprobe failed: 1
  raid1: Required device-mapper target(s) not detected in your kernel.
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

