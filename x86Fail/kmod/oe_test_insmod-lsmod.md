# oe_test_insmod-lsmod

测试套问题， x86 和 riscv 失败原因相同，具体原因不同，均与测试套 Line 28-29 有关

```
    raid0Path=$(find /usr/lib/modules/ -name raid0.ko)
    faultyPath=$(find /usr/lib/modules/ -name faulty.ko)
```

在 x86 和 riscv 下，运行后两个变量均为空。

在 riscv 下，由于两个模块缺失，故 find 没有输出；而在 x86 下，则由于两个模块实际名称为 raid0.ko.xz 和 faulty.ko.xz ，导致 find 没有找到两个模块的路径。

