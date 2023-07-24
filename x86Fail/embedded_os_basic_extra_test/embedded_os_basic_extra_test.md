### embedded_os_basic_extra_test

报错log均为尝试给/bin/文件夹内文件添加权限时报错，bin内均无所需文件

例：

```
+ setcap cap_linux_immutable=eip /bin/chattr.e2fsprogs
Failed to set capabilities on file '/bin/chattr.e2fsprogs': No such file or directory
```

#### 