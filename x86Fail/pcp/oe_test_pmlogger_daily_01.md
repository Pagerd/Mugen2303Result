### oe_test_pmlogger_daily_01：测试套没有更新

riscv与x86报错均相同

在使用egrep时报出以下错误

```
+ /usr/libexec/pcp/bin/pmlogger_daily -N
+ grep 'rm -f /var/lib/pcp/tmp/pmlogger/primary'
egrep: warning: egrep is obsolescent; using grep -E
```

正确写法应为 grep -E