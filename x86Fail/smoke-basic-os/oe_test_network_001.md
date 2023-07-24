### oe_test_network_001:ethtool错误

riscv没有安装ethtool

```
+ ethtool ''
oe_test_network_001.sh: line 42: ethtool: command not found
```

同时添加了一个无效的dev

```
Device "" does not exist.
+ ip addr add 192.1.1.11 dev ''
```

在x86上则在使用ethtool时报错

```
+ ethtool ''
netlink error: no device matches name (offset 24)
netlink error: No such device
netlink error: no device matches name (offset 24)
netlink error: No such device
netlink error: no device matches name (offset 24)
netlink error: No such device
netlink error: no device matches name (offset 24)
netlink error: No such device
netlink error: no device matches name (offset 24)
netlink error: No such device
```

