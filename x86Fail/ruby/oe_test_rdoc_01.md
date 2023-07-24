### oe_test_rdoc_01:加载未指定的Regexp类

riscv与x86报错相同

对应log如下

```
+ rdoc ../common/main.rb --dry-run
+ grep 'Parsing sources'
uh-oh! RDoc had a problem:
Tried to load unspecified class: Regexp

run with --debug for full backtrace
```

