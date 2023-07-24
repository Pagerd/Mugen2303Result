### oe_test_pmhostname_pmlock_pmlogger_check：测试文件错误

riscv与x86有不同的报错log

riscv在使用pmlogger_check时出错

```
+ /usr/libexec/pcp/bin/pmlogger_check -NV
+ grep 'compressing PCP archives for host local:'
+ CHECK_RESULT 1
+ actual_result=1
```

而x86在使用test -z时出错

```
+ test -z 78490 78561
oe_test_pmhostname_pmlock_pmlogger_check.sh: line 49: test: 78490: binary operator expected
```

