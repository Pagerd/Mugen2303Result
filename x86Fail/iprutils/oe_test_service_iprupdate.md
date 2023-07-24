# oe_test_service_iprupdate

测试套问题， x86 和 riscv 失败原因一致

测试套测试 iprupdate.service ，该 daemon 由 iprutils 软件包提供，而测试脚本没有显式安装， x86 和 riscv 镜像也没有预装

```
+ systemctl restart iprupdate.service
Failed to restart iprupdate.service: Unit iprupdate.service not found.
```

