### oe_test_storage_DevMgmt_disk_operation：dev挂载错误

riscv报错log为

```
+ parted /dev/vdb
+ grep -iE 'error|fail' log
Error: /dev: unrecognised disk label
+ CHECK_RESULT 0 1
```

x86对应报错为

```
+ grep 'Using /dev/vdb' log
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

