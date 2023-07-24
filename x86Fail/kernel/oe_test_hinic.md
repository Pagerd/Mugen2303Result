# oe_test_hinic

x86 和 riscv 失败原因不同

## x86 上

测试套问题，测试命令行如下

```
    kernel_name=`uname -r`
    test -f /lib/modules/${kernel_name}/kernel/drivers/net/ethernet/huawei/hinic/hinic.ko
    CHECK_RESULT $? 0 0 "file does not exist"
```

导致错误

```
+ kernel_name=6.1.19-7.0.0.17.oe2303.x86_64
+ test -f /lib/modules/6.1.19-7.0.0.17.oe2303.x86_64/kernel/drivers/net/ethernet/huawei/hinic/hinic.ko
+ CHECK_RESULT 1 0 0 'file does not exist'
```

实际上内核模块存在，正确的路径为 ``/lib/modules/6.1.19-7.0.0.17.oe2303.x86_64/kernel/drivers/net/ethernet/huawei/hinic/hinic.ko.xz`` ，文件名和预期不同。

## riscv 上

riscv 内核缺失 hinic 模块

```
+ modinfo hinic
+ grep -i version
modinfo: ERROR: Module hinic not found.

+ modprobe hinic
modprobe: FATAL: Module hinic not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
```

