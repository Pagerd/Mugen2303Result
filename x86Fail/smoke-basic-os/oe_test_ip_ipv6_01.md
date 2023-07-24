### oe_test_ip_ipv6_01：地址错误

riscv与x86报错相同

下为对应log

```
+ ip -6 address add 1001::1/64 dev label :1
Error: either "local" is duplicate, or ":1" is a garbage.
```

