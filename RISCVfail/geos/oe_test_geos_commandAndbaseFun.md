##### oe_test_geos_commandAndbaseFun:

测试环境没有安装kernel-headers,下为log内对应报错部分

```
+ g++ geos_test.cpp -o geos_test
In file included from /usr/include/errno.h:28,
                 from /usr/include/c++/10.3.1/cerrno:42,
                 from /usr/include/c++/10.3.1/ext/string_conversions.h:44,
                 from /usr/include/c++/10.3.1/bits/basic_string.h:6545,
                 from /usr/include/c++/10.3.1/string:55,
                 from /usr/include/c++/10.3.1/bits/locale_classes.h:40,
                 from /usr/include/c++/10.3.1/bits/ios_base.h:41,
                 from /usr/include/c++/10.3.1/ios:42,
                 from /usr/include/c++/10.3.1/ostream:38,
                 from /usr/include/c++/10.3.1/iostream:39,
                 from geos_test.cpp:1:
/usr/include/bits/errno.h:26:11: fatal error: linux/errno.h: No such file or directory
   26 | # include <linux/errno.h>
      |           ^~~~~~~~~~~~~~~
compilation terminated.
```

在测试套内添加安装kernel-headers命令后测试通过