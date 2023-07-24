### oe_test_ip_ipv6_04:没有对应device

riscv与x86报错相同

下为对应报错log

```
+ ifconfig inet6 add 4::4/64
SIOGIFINDEX: No such device
+ CHECK_RESULT 1 0 0 'Failed to add ipv6 4::4'
```

