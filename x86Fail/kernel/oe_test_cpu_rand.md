# oe_test_cpu_rand

x86 和 riscv 失败原因基本一致

测试命令如下

```
    lscpu | grep rand
    CHECK_RESULT $? 0 0 "The random number generation function is not supported"
    grep ARCH_RANDOM=y /boot/config-$(uname -r)
    CHECK_RESULT $? 0 0 "The random number generation function is not supported"
```

两个测试行在两个架构的 qemu 虚拟机上均失败。

另外在 x86_64 的 qemu 上若添加 ``-cpu qemu64,+rdrand`` 可以使第一个测试行通过。

