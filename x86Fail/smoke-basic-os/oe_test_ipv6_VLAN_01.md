### oe_test_ipv6_VLAN_01：dev错误

riscv与x86报错相同

下为报错log

```
+ ip link add dev vlan.1 link type vlan id 1
Error: either "dev" is duplicate, or "vlan" is a garbage.
+ CHECK_RESULT 255 0 0 'Failed to add VLAN'
```

