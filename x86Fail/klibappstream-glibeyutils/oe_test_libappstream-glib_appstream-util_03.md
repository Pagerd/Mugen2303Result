# oe_test_libappstream-glib_appstream-util_03

测试套原因， x86 和 riscv 失败原因相同， grep 没有过滤到指定字串

测试语句 Line 52-53 如下

```
    appstream-util -v --profile --nonet query-installed 2>&1 | grep "http://www.ezix.org/project/wiki/HardwareLiSter"
    CHECK_RESULT $? 0 0 "Check appstream-util -v --profile --nonet query-installed failed"
```

失败日志

```
+ appstream-util -v --profile --nonet query-installed
+ grep http://www.ezix.org/project/wiki/HardwareLiSter
+ CHECK_RESULT 1 0 0 'Check appstream-util -v --profile --nonet query-installed failed'
```

