### oe_test_nftables_anonymous_map:测试环境没有安装对应预装软件

riscv与x86报错均相同

在配置环境时候使用了nft，但是测试镜像未安装nft

```
+ nft add table inet example_table
oe_test_nftables_backup_rules.sh: line 24: nft: command not found
+ nft add chain inet example_table example_chain '{' type filter hook input priority 0 ';' policy accept ';' '}'
oe_test_nftables_backup_rules.sh: line 25: nft: command not found
```

