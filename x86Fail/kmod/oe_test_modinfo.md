# oe_test_modinfo

x86 和 riscv 原因不同

x86 在以下测试失败

```
    modinfo -p raid1 | grep -E "max_queued_requests|int"
    CHECK_RESULT $?
```

日志如下

```
+ modinfo -p raid1
+ grep -E 'max_queued_requests|int'
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
```

而 riscv 则缺失 dm_log 和 raid1 模块，导致失败

