### oe_test_nftables_anonymous_map:测试环境没有安装对应预装软件

riscv与x86报错均相同

在配置环境时候使用了nft，但是测试镜像未安装nft

```
+ nft add table inet sec010
oe_test_nftables_anonymous_map.sh: line 33: nft: command not found
+ nft add chain inet sec010 tcp_packets_010
oe_test_nftables_anonymous_map.sh: line 34: nft: command not found
+ nft add rule inet sec010 tcp_packets_010 counter
oe_test_nftables_anonymous_map.sh: line 35: nft: command not found
+ LOG_INFO 'End to prepare the test environment.'
```

