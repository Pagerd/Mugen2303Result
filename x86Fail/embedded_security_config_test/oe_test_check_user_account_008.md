#### oe_test_check_user_account_008:/etc/motd内没有相关信息

对应报错log如下

```
+ egrep -v '^\s*#|^\s*$' /etc/motd
+ CHECK_RESULT 1 0 0 'not set /etc/motd hello message'
+ actual_result=1
+ expect_result=0
```

### 