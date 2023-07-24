##### oe_test_check_file_sys_protect_004: 目录内没有对应文件

log内对应报错如下

```
+ find /init -type l -user root -group root -perm 777
find: ‘/init’: No such file or directory
+ CHECK_RESULT 1 0 0 'check /init file right fail'
+ actual_result=1
```

##### 