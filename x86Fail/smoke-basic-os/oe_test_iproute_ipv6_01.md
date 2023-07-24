### oe_test_iproute_ipv6_01:命令行不完整

riscv与x86报错相同

下为对应报错log

```
+ ip -6 route add 1001::2/64 dev
Command line is not complete. Try option "help"
+ CHECK_RESULT 255 0 0 'Failed to add ipv6 route 1001::2'
```

