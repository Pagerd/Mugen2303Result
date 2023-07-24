# oe_test_ip6tables-save

测试套问题， x86 和 riscv 失败原因一致

测试套 Line 30-31 如下

```
    ip6tables-save | grep -A 200 nat | grep -A 100 mangle | grep -A 80 raw | grep -A 60 security | grep filter
    CHECK_RESULT $? 0 0 "Incomplete display"
```

实际没有出现这些字段

