### oe_test_ip_ipv6_02:命令行不完整

riscv与x86报错相同

下为对应报错log

```
+ ip -6 addr add 4::4/64 dev
Command line is not complete. Try option "help"
+ CHECK_RESULT 255 0 0 'Failed to add ipv6 4::4'
```

