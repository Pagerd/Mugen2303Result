# oe_test_system_log_recorded

测试套问题， x86 和 riscv 失败原因基本一致

测试套 Line 25

```
folder=$(ls /run/log/journal/)
```

在 riscv 上 ${folder} 为空，而在 x86 上可能有多个目录，这两种情况测试套没有进行检查，导致测试失败。

