### oe_test_erb:测试套编写错误

riscv与x86报错均相同

```
+ erb --version
+ grep 'erb.*[0-9]'
+ CHECK_RESULT 1
+ actual_result=1
```

实际版本显示为

```
[root@localhost mugen-riscv]# erb --version
2.2.3
```

