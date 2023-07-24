### oe_test_nftables_variable_map:测试环境没有安装对应预装软件

riscv与x86报错均相同

在测试时使用nft，但是测试镜像未安装nft，因此也无nftables.service

```
+ systemctl restart nftables.service
Failed to restart nftables.service: Unit nftables.service not found.
```

