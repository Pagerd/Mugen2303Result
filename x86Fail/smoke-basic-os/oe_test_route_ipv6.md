### oe_test_route_ipv6：不支持指定的指令

riscv与x86报错相同

下为报错log

```
+ route -A inet6 add 5001::/64 dev
Usage: inet6_route [-vF] del Target
       inet6_route [-vF] add Target [gw Gw] [metric M] [[dev] If]
       inet6_route [-FC] flush      NOT supported
```

