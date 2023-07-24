# oe_test_service_ebtables

测试套问题， x86 和 riscv 失败原因相同。

测试脚本测试 ebtables 软件包，但是没有显示安装 ebtables ， riscv 和 x86 也没有预装 ebtables 。

```
+ test_restart ebtables.service
+ service=ebtables.service
+ systemctl restart ebtables.service
Failed to restart ebtables.service: Unit ebtables.service not found.
```

