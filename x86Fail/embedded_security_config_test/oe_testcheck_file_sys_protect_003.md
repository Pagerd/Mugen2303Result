##### oe_testcheck_file_sys_protect_003:audit内没有log文件

log内对应报错如下

```
+ find /var/log/audit/audit.log -type f -user root -group root -perm 600
find: ‘/var/log/audit/audit.log’: No such file or directory
+ CHECK_RESULT 1 0 0 'check /var/log/audit/audit.log file right fail'
+ actual_result=1
```

##### 