# oe_test_keyutils-api

测试套问题， x86 和 riscv 失败原因一致

测试需要 keyutils.h ，该头文件由 keyutils-libs-devel 提供，而该软件包没有被显式安装

失败日志如下

```
+ make
gcc -lkeyutils t_request_key.c -o test_key
t_request_key.c:4:10: fatal error: keyutils.h: No such file or directory
    4 | #include <keyutils.h>
      |          ^~~~~~~~~~~~
compilation terminated.
make: *** [Makefile:4: all] Error 1
```

