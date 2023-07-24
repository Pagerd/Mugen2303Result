# oe_test_service_iprdump

测试套问题， x86 和 riscv 失败原因一致

测试套测试 iprdump.service ，该 daemon 由 iprutils 软件包提供，而测试脚本没有显式安装， x86 和 riscv 镜像也没有预装

```
+ systemctl restart iprdump.service
Failed to restart iprdump.service: Unit iprdump.service not found.
```

