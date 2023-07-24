### oe_test_IPV6_traceroute6_02：local错误

riscv与x86报错相同

对应报错log如下

```
+ ip -6 address add fe80::2e0:fcff:fe09:fffd/64 dev scope link
Error: either "local" is duplicate, or "link" is a garbage.
+ ip -6 address add fe80::2e0:fcff:fe09:fffe/64 dev scope link
Error: either "local" is duplicate, or "link" is a garbage.
```

