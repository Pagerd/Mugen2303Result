### oe_test_nftables_listen_package:测试环境没有安装对应预装软件

riscv与x86报错均相同

在测试时使用nft，但是测试镜像未安装nft

```
+ nft add chain inet sec012 sec012_chain '{' type filter hook input priority 0 ';' policy accept ';' '}'
oe_test_nftables_create_counters.sh: line 37: nft: command not found
```

