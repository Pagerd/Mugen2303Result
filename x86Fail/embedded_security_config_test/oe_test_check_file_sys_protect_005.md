##### oe_test_check_file_sys_protect_005:设置默认权限错误

log内对应报错如下

```
++ umask
+ umaskValue=0022
+ test 0022 == 0077
+ CHECK_RESULT 1 0 0 'check umask default value fail'
+ actual_result=1
+ expect_result=0
......
+ grep '[umaskUMASK][[:space:]]\+077'
+ grep -iE '^\s*umask\s+' /etc/profile
+ CHECK_RESULT 1 0 0 'check /etc/profile set umask value fail'
+ actual_result=1
+ expect_result=0
```

##### 