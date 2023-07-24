# oe_test_depmod

测试套问题， x86 和 riscv 原因不同，但是均为 Line 34-39 的问题

```
    symversPath=$(find / -name Module.symvers)
    depmod -e -E $symversPath
    CHECK_RESULT $?
    mapPath=$(find / -name System.map)
    depmod -e -F $mapPath
    CHECK_RESULT $?
```

在 x86 上， ``symversPath`` 和 ``mapPath`` 均为空，故后续测试全部失败。

在 riscv 上， ``symversPath`` 正常；而 ``mapPath`` 找到了两个，导致与其相关的测试失败。

