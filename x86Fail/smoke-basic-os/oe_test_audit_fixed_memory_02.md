### oe_test_audit_fixed_memory_02:没有对应的asm库

riscv与x86报错并不相同

riscv上显示为缺少asm从而无法编译

```
+ gcc -laudit test.c
In file included from test.c:3:
/usr/include/libaudit.h:26:10: fatal error: asm/types.h: No such file or directory
   26 | #include <asm/types.h>
      |          ^~~~~~~~~~~~~
compilation terminated.
```

x86则因为测试镜像并未安装gcc导致测试用例不通过

```
+ gcc -laudit test.c
oe_test_audit_fixed_memory_02.sh: line 45: gcc: command not found
```

