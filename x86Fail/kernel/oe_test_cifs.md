# oe_test_cifs

x86 和 riscv 失败原因不同

## 内核问题

riscv 内核 cifs 模块缺失

```
+ modprobe cifs
modprobe: FATAL: Module cifs not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
```

x86 在 rmmod cifs 后还遗留 cifs_arc4 和 cifs_md4 模块，导致测试失败

```
    rmmod  cifs
    CHECK_RESULT $? 0 0 "vport-geneve remove failure"
    lsmod | grep  cifs
    CHECK_RESULT $? 0 1 "vport_geneve exist"


+ lsmod
+ grep cifs
cifs_arc4              16384  0
cifs_md4               16384  0
+ CHECK_RESULT 0 0 1 'vport_geneve exist'
```

## 测试套问题

测试脚本测试的是 cifs 模块，但是错误信息是 vport_geneve 模块

且最后一个测试也是测试的 vport_geneve 模块，和测试套目的不相符合

```
function run_test() {
    modinfo cifs |grep cifs
    CHECK_RESULT $? 0 0 "Description Module information failed to be displayed"
    lsmod | grep  cifs
    CHECK_RESULT $? 0 1 "Default installation"
    modprobe cifs
    CHECK_RESULT $? 0 0 "Module loading failure"
    lsmod | grep  cifs
    CHECK_RESULT $? 0 0 "vport_geneve not found"
    rmmod  cifs
    CHECK_RESULT $? 0 0 "vport-geneve remove failure"
    lsmod | grep  cifs
    CHECK_RESULT $? 0 1 "vport_geneve exist"
    dmesg | grep "vport_geneve" | grep -Ei 'error|fail'
    CHECK_RESULT $? 1 0 "error message was reported"
}
```

