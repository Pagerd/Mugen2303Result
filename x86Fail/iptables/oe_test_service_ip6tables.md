# oe_test_service_ip6tables

测试套问题， x86 和 riscv 失败原因一致

测试套测试 ip6tables.service ，该 daemon 由 iptables 软件包提供，但是测试脚本没有显式安装它，而 x86 和 riscv 镜像也都没有预装该软件包，导致测试失败

```
+ systemctl restart ip6tables.service
Failed to restart ip6tables.service: Unit ip6tables.service not found.
```

