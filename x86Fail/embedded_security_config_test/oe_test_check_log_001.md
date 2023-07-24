##### oe_test_check_log_001:audit内没有rules文件

log内对应报错如下

```
+ grep '\-w /var/log/lastlog -p wa -k logins' /etc/audit/audit.rules
grep: /etc/audit/audit.rules: No such file or directory
+ CHECK_RESULT 2 0 0 'check /etc/audit/audit.rules set fail'
+ actual_result=2
+ expect_result=0
+ mode=0
+ error_log='check /etc/audit/audit.rules set fail'
+ exit_mode=0
```

