### oe_test_storage_lvm_create_cache：找不到对应设备/没有预装对应软件

riscv对应报错如下

```
+ expect -c '
    set timeout 30
    log_file testlog1
    spawn lvcreate --type raid5 -i 3 -L 50MB -n test1 openeulertest -y
    expect "*\[y/n\]*" {send "y\r"}
    expect eof
'
spawn lvcreate --type raid5 -i 3 -L 50MB -n test1 openeulertest -y
modprobe: FATAL: Module dm-raid not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
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

