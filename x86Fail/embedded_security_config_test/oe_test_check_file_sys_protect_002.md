##### oe_test_check_file_sys_protect_002: 目录内没有对应文件

log内对应报错如下

```
+ find /etc/securetty -type f -user root -group root -perm 600
find: ‘/etc/securetty’: No such file or directory
+ CHECK_RESULT 1 0 0 'check /etc/securetty file right fail'
+ actual_result=1
+ expect_result=0
```

##### 