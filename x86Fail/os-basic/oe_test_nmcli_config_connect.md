# oe_test_nmcli_config_connect

x86 和 riscv 原因一致

```
+ nmcli con up ethernet-eth1 ifname eth1
Error: Connection activation failed: IP configuration could not be reserved (no available address, timeout, etc.)
Hint: use 'journalctl -xe NM_CONNECTION=7cbe3891-1806-4754-878b-ddbcc7e280c7 + NM_DEVICE=eth1' to get more details.
```

但是测试脚本并没有导出 journalctl 日志。

