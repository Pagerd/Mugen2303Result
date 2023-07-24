# oe_test_service_irqbalance

测试套问题， x86 和 riscv 失败原因一致

测试套测试 irqbalance.service　，该 daemon 由 irqbalance 软件包提供，但是测试套没有显式安装它，而 x86 和 riscv 镜像也没有预装这个软件包，导致测试失败

```
+ systemctl restart irqbalance.service
Failed to restart irqbalance.service: Unit irqbalance.service not found.
```

