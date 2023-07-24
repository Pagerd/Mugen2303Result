### oe_test_libxml2_002:缺少软件预装包

riscv上为g++命令时出错

```
+ g++ createxml.cpp -o createdxml -I /usr/include/libxml2/ -L /usr/local/lib -lxml2 -lm -lz
In file included from /usr/include/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/limits.h:195,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/syslimits.h:7,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/limits.h:34,
                 from /usr/include/libxml2/libxml/tree.h:16,
                 from /usr/include/libxml2/libxml/parser.h:16,
                 from createxml.cpp:3:
/usr/include/bits/local_lim.h:38:10: fatal error: linux/limits.h: No such file or directory
   38 | #include <linux/limits.h>
      |          ^~~~~~~~~~~~~~~~
compilation terminated.
+ test -f /tmp/createdxml
+ CHECK_RESULT 1 0 0 'compile testfile fail'
```

x86则为未安装g++

```
+ g++ createxml.cpp -o createdxml -I /usr/include/libxml2/ -L /usr/local/lib -lxml2 -lm -lz
oe_test_libxml2_001.sh: line 73: g++: command not found
```

