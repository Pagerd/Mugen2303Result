### oe_test_mtr：dns错误

riscv与x86报错均相同

```
+ mtr -r dns.google
+ grep dns.google
+ CHECK_RESULT 1 0 0 'mtr -r dns fail'
```

