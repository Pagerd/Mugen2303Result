# oe_test_check_huge_task

x86 和 riscv 失败原因一致，没有找到搜寻的内核配置

测试语句如下

```
    grep -w CONFIG_BOOTPARAM_HUNG_TASK_PANIC_VALUE=0 /boot/config-`uname -r`
    CHECK_RESULT $? 0 0 "BOOTPARAM_HUNG_TASK_PANIC_VALUE ERROR"
```

在两个架构上均为空

```
+ grep -w CONFIG_BOOTPARAM_HUNG_TASK_PANIC_VALUE=0 /boot/config-6.1.8-3.oe2303.riscv64
+ CHECK_RESULT 1 0 0 'BOOTPARAM_HUNG_TASK_PANIC_VALUE ERROR'

+ grep -w CONFIG_BOOTPARAM_HUNG_TASK_PANIC_VALUE=0 /boot/config-6.1.19-7.0.0.17.oe2303.x86_64
+ CHECK_RESULT 1 0 0 'BOOTPARAM_HUNG_TASK_PANIC_VALUE ERROR'
```

