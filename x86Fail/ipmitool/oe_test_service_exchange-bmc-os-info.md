# oe_test_service_exchange-bmc-os-info

测试套问题， x86 和 riscv 失败原因一致

测试对象 exchange-bmc-os-info.service ，由 exchange-bmc-os-info 软件包提供

软件包在 x86 和 riscv 均没有预装，且测试脚本没有显示安装，导致测试失败

```
+ systemctl restart exchange-bmc-os-info.service
Failed to restart exchange-bmc-os-info.service: Unit exchange-bmc-os-info.service not found.
```

