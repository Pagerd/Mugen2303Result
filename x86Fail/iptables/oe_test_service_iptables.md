# oe_test_service_iptables

测试套问题， x86 和 riscv 失败原因一致

测试套测试 iptables.service ，该 daemon 由 iptables 软件包提供，但是测试脚本没有显式安装它，而 x86 和 riscv 镜像也都没有预装该软件包，导致测试失败

```
+ systemctl restart iptables.service
Failed to restart iptables.service: Unit ip6tables.service not found.
```

