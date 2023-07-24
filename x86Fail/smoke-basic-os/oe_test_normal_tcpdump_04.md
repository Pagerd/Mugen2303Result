### oe_test_normal_tcpdump_04:测试套编写错误

riscv与x86报错相同

```
+ tcpdump -i -c 10
ping: usage error: Destination address required
+ CHECK_RESULT 1 0 0 'tcpdump -i  -c 10:failed'
+ actual_result=1
```

