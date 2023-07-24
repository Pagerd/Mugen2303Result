##### oe_test_check_network_firewall_002:版本更新测试套没有跟上

log内对应报错如下

```
+ check_version 1 net.ipv4.conf.all.accept_redirects
+ grep -q 22.03
+ grep VERSION_ID /etc/os-release
+ '[' 1 -eq 0 ']'
+ CHECK_RESULT 1 0 0 'check net.ipv4.conf.all.accept_redirects set fail'
+ actual_result=1
```

测试使用的版本为23.03而测试套检测的是22.03版本